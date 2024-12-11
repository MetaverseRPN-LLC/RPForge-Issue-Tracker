# Items Overhaul Migration Post Mortem, or how a 4 hour maintenance spiralled into a 6 hour maintenance and multi-day reduced functionality period

Hello all, this document is intended to help breakdown and explain how our most recent maintenance turned into the multi-day reduced functionality period it has now spiralled into
## So what exactly happened here?
First, some key background around what this maintenance was for. Some of you may recall an incident regarding bugs with inventory around the beginning of July of this year, where many features regarding items seemed to break out of nowhere. The day before these reports came in we had implemented a major change to the database backend regarding items, splitting inventory items and their respective templates into their own tables in order to better optimize how items were handled across the board, and eventually to power features better like the tagged inventory we had recently implemented. 
Unfortunately, due to a multitude of factors, a slew of bugs cropped up from the migration, and as a result this migration had to be reverted temporarily until we could figure out a better way to handle it in the future.
## What went wrong the first time?
A multitude of things, though a short list of our mistakes during the first round can be found below
- Miscalculating how big an impact this change would be on the backend
- Only updating the create item method and instantiate methods to the new database methods.
- Attempting to make this massive shift using AsyncPG rather than SQLAlchemy
- Not shutting the bot down during the Migration in order to reduce downtime as much as humanely possible.

All of which contributed in some manner of another to us reverting the migration a few days later in it's entirety. However, this was not a clean reversion, as some items were created only on the new tables, which resulted in several days to weeks of us having to manually move items that were either created, or given to a character during the 72 hours the migration was active, from the newer tables back to the old tables.
## What did you learn from all of this?
Over the past several months after this attempted migration, we have been working to slowly overhaul our database methods for every feature of the bot, migrating all methods off of our current/old adapter library(AsyncPG) to now use SQLAlchemy for all possible methods. SQLAlchemy comes with many many advantages over our old method to access the database, most notably, increased speed and efficient data access(SQLAlchemy is what allowed for the Ludicrous update, which as we confirmed, allowed for pulling up over 1000+ characters and items in a single incident, something that used to take several minutes via the older methods).
## So it was time for round 2?
Yes. After ample testing, and confirmation that these methods would work for what we needed to, we decided in late November, to begin the process of reimplementing the Item Migration we attempted previously, this time, updating all functions that used items at the same time to ensure no bugs like before would occur. This would inherently require us to update these features as well:
- Shops
- Markets
- Recipes
- Lootboxes

Updating Shops to use SQLAlchemy would also allow us to implement some of the features requested by our users like Limited Stock in the future, so this would have been a net benefit across the board.

There were also going to be some major changes to how we would handle the migration this time around. 
## What was the plan to ensure this wouldn't end up like last time?
Having learned a lot from the last time we did this, we made attempted to make sure that when we attempted the migration this time, it would go off as seamlessly as we could possibly make it. We also expanded the migration to include a change to how we handle tags for items. This has resulted in the new migration including several key parts
- Creating a new table for storing tags for items
- Creating a new table for storing tagged items with their tags
- Migrating all Item Database methods to point to the new tables
- Migrating all Shop database methods to be compliant with the new methods for item handling
- Migrating all Market methods
- Migrating all Recipe Methods
- Migrating all Lootbox Methods
- Testing ALL of the above to make sure there are no errors before even beginning to touch Prod
- Copying all Item Templates to the new table for storing only item templates
- Copying all Inventory Items to the new table for storing only inventory items
- Recreating all tags using the new method
- Storing tagged items in the new tagged items table

## So how'd that plan work out for ya'll?
As we continue with the migration, I am happy to say that every step of this plan, save for the last 2 have gone off without a hitch. We were able to successfully migrate all methods to point to the brand new tables, and have undergone extensive testing of all commands that used items to make sure that everything is working.

## If that's the case, why are we still almost a day into the migration?
That can be traced to two particular issues. First, let me explain how tags were originally stored in the DB:
All items, whether template or otherwise, were stored in a single table, which we will call Items. This table had all the data for an item, it's name, emoji, description, what template it inheritied it's data from, if any at all, as well as it's Tags. Tags in particular was stored in an Array within a single column of the table. This is part of why our initial attempt to implement a tag sorted inventory turned into the mess it did. As part of our migration efforts, I planned to completely overhaul how we handled tags, giving them a completely different table and a unique ID for every tag in the bot. That way I could reimplement the sorting method, and even allow for our users to determine the exact order they wanted the tags to be displayed in within the tag sorted inventory.
## I see... But wouldn't that mean all those tags would need to be recreated and migrated over as well to the new system?
Exactly, and now you can see why we are in the situation we are in now. As of me typing this up, we are 55000 tagged_items in to a 376,706 item migration. One that I was hoping would have finished during the 5 hour maintenance window, but once I already overshot it by an extra 2 hours, I realized this was going to take far longer than I could afford to shut the bot down for.

As such, at around 6:05 PM EST, we turned the Bot back on, and informed our users that certian features may not be functional until the migration was complete. 

## Understandable.. But the item cog wasn't disabled until later than that right?

That is correct, I disabled the Item Module as of 5:47 AM EST after noticing a high level of errors were occuring related to items. Out of concern for potential data corruption occuring from these errors, I manually disabled both the Item and Inventory modules, to ensure nothing would touch the item database until this migration was complete.

## So what can we learn from this one?
The biggest thing we can learn from this particular incident, is how long it takes to do a manual migration like this. We are now over 19 hours into this particular maintenance and the bulk of the time has come from the tag migration. In the future, we will definitely need to setup a method to better handle migrations of this level at a more efficient timescale.

One thing we have learned from this update is how many of our users appear to not be in the support server. There were many people who joined during the outage completely unaware that this was a planned maintenance. In order to rectify this, in the coming weeks, we plan to implement a setting to allow users to recieve announcements we make directly in their servers from the bot itself, this will be released in a QOL update later along with a new first time setup menu to help point people towards setting this new announcement feature up, along with many other features for the bot.
