Hello and welcome to RPGBot!

Before we get started heres a general overview to give you an understanding of what this bot is and isn't:

## What RPGBot provides


- Characters
    - can have custom attributes
    - you can talk as
    - can have their own money and inventories
- Item system
    - custom items
    - optionally useable
    - customizable craftingsystem
- Economy System
    - custom currency name
    - lotteries
    - salaries
    - server shop
    - player trading
    - player market
   
RPGBot is a tool to help you do your own RPGs, there is no game to play without you setting it up first.

> Note: throughout this tutorial commands will be shown with the following syntax:
>
> Prefix Command Arguments
>
> Prefix in this tutorial will be the default prefix rp! (you can set a custom one)
> 
> Command will be a word right after the prefix with no space between the two (you cannot customize these)
>
> Some commands are subcommands, meaning they need to be used with another command to work these will show up as additional words after the command and there can be more than one
>
> Arguments will be surrounded by one of two symbols and you are meant to replace them with what you want in there
>
>\<name> : required argument (please dont put just name in there)
>
>[name]: optional argument
>
>
>So as an example the command
>
>rp!character \<name>
>
>Is meant to be used like this:
>
>rp!character Henry
>
>In addition some commands will have (Mod) next to them meaning you need to have a role called "Bot Admin" on yourself to use those. This Role doesn't need special permissions it just needs that exact name(case sensitive)
>
>If something doesn't work and involves an item or a character with spaces in its name try putting " these around it like "this" to signal to the bot where one thing ends and the other begins

**Any time you are confused as to how to use a command or want to see subcommands for a command, please look at the help for that command, for example**

> rp!help bank
> rp!help character assume
> rp!help

The help can provide instant information on using commands. If a command does not appear to be listed, it is probably a subcommand of another command!

Now that thats out of the way lets get into how to use those things

## Managing Settings and Setting Up a Server

RPGBot is configurable, and provides many options to fit your server needs.

### Language

> rp!settings setlanguage <language>
    
You can use this command to set the bot to use a certain language for your server. See the help on the command for details, currently the bot supports several languages including english, spanish, french, german, and portuguese. We are always looking for help with translations, so if you would like to contribute, please contact us in the support server!

### Prefix

> rp!settings setprefix <prefix>
    
A custom prefix can be configured for your server, this is independent from character prefixes and acts as a general replacement for rp!

### Character Assumption and Webhooks

> rp!settings usewebhooks <yes/no>

When characters are assumed, by default their messages will be replaced by a webhook that has their character's name and icon, with the content of the message. This can be disabled by setting usewebhooks to `no`.

### Disabling and Enabling Commands

> rp!settings disable <command> <role>
> rp!settings enable <command> <role>
> rp!settings clearcommand <command> <role>
    
Every command has 3 options, either it is enabled for a given role (bypassing moderator restrictions), disabled for a given role (not bypassing moderator restrictions), or it has no setting, and defers to the default option of whether it is for moderators or not. Bot Moderators bypass all settings for disabled and enabled commands. For example, if the `character create` command is disabled for `@everyone`, then nobody but moderators may make characters. If the command `givemoney` is enabled for the `Money Givers` (any role can be targeted), then anyone with the `Money Givers` role may use the command, in addition to Bot Moderators. Use `settings clearcommand` to clear the settings for a command.

### Guild Costs

> rp!settings setguildcost <cost>

Guilds can be configured to require a certain cost to be made by players. Players will be charged the given amount when attempting to create a guild.

### Character Roles

> rp!character addrole <role> [target]
> rp!character removerole <role> [target]
    
Characters can be given roles for targeting things like giving items, money, and for managing salaries. These roles are standard Discord roles, to add a role, you must first create it through Discord. Having the Bot Moderator role on a character has no effect.

## Characters

All bot features require having a character tied to your command. If you were a fan of having data tied to your user account, we recommend you use the Default Character functionality, it will make the bot operate nearly as if the character weren't there.

### Creation

rp!character create \<name>

A prompt will come up asking you to type in a number for the category you want to edit you can either do that or click the reaction arrow that points to the right to go through this process. When you feel like you're done you can finish the process with the green checkmark reaction

Now lets dive into the categories you have access to

- Description
   
   This is a little summary of your character, its not important for mechanics and entirely flavour
   
- Picture

    A link to a picture that will show up when someone looks at your character or you assume the character
    
- Prefix

    A prefix you can quickly use to talk as the character or use a command as them, for example, instead of having to assume the character with `rp!char assume`, you can instead use the custom prefix you've set for the character to use the character for that command, for example, `rp!bank deposit 500` while assumed can be made `>bank deposit 500` while not explicitly assumed.
    
    
Now that you have made your character lets jump through the basic other usages

### Assume

> rp!character assume \<name>

You can use this to become your character in a manner of speaking, the bot can only do this if it has the Manage Messages and Manage Webhooks Permissions
to undo it you can use 

> rp!character unassume

While assumed your sent messages will be deleted and replaced by the bot saying it with your assumed character's image as profile picture and with the original content of your message. When using a custom prefix, the bot will replace normal messages that begin with <prefix>/message (with a slash between the prefix and message)

Alternatively, if you do not want the bot to replace your messages, you can set a default character with

> rp!character default \<name>

Or you can give the character a custom prefix to quickly switch between characters. If a character is given the prefix `!`, any command run with the prefix `!` will be run as that character, and if another character has the prefix `?`, then these two can be used to quickly run commands as different characters without assuming. Prefixes will override the selected assumed character, which will in turn override the selected default character.

Most commands on this bot will require you to use them as a character, whether you use the assume command or the character prefix for that doesnt matter. If you do not want the bot to resend messages with the custom character, you can disable it in the server settings with

> rp!settings usewebhooks false (as a moderator)

It is generally easier to use a custom prefix than to assume, see the creation section above for details.

### Edit

> rp!character edit \<name>

This command lets you edit already made characters

### Lookup

> rp!character \<name>
> rp!mychars 
> rp!characters

You can list characters or find them by name


## Items

> Small Note:
>
> You need a character to actually have access to an inventory

### Creation

> rp!item create \name

Before you can do anything with items you need to create at least one

##### Description
- Flavour text, no mechanical impact

##### Picture
- A link to an image that shows up when someone looks up the item

##### Type
- several tags you can add for unique effects, the bot explains the tags in the creation prompt

## The Economy as a Player

### Balance and Bank

> rp!balance [character]

Lets you check how much money you have in your pockets and in your bank, if you just made your character you probably have nothing on you but the starter amount. You can optionally target a character to see their balance.

> rp!bank withdraw <amount>
> rp!bank deposit <amount>

You can withdraw and deposit into your bank with these commands. You can only spend money that is on you, so be sure to withdraw from the bank if you do not have enough.

## Transactions with players

> rp!trade <target>
> rp!give [items...] [targets...]
> rp!pay <amount> <target>

## Shops and Purchases

## Collecting Salaries

## Managing the Economy

> Note:
>
> You need a character to use or be targeted by these commands as only characters can have money or inventories

Managing the economy is done with a number of commands. The economy ties together the inventory system, character system, and several other systems. Money can be made in a number of ways: a starting amount granted to new players, manually given by moderators, earned with salaries on a regular basis, or by selling items to the shop.

### Giving and Taking Money as a Moderator

> rp!givemoney \<amount> [targets...]
> rp!takemoney \<amount> [targets...]

This can be used to directly give and take money from characters. You can target users (who are assumed), characters by name, and roles which characters may have.

### Salaries

You will first off have to create discord roles to give salaries to. When you have the role made use the following command
> rp!salary create \<role>

For the role you can either ping it or type its name (use one " on each side "like this" if it has multiple words)


### Shop and Market

## Lootboxes and Chance

### Lootbox Management

### Lotteries

## Crafting and Recipes

## Premium Features

## Migrating from RPGBot V1
You can migrate data from v1 to v2 with this handy command:

> rp!import rpgbot \<datatype> [overwrite]

The available datatypes are
- items
- characters
- shops

Please import them in this order to ensure that the bot can work them properly
Disclaimer: the items and balance in your non character inventory wont be imported, we will release a patch for this soon
You dont need to add the overwrite unless you want to overwrite existing data on v2
if you do want to do that just type overwrite


## Importing Data with Spreadsheets
Many features of the bot can be imported from .csv files, which can be generated from Excel spreadsheets. Below are example spreadsheets
See the csv_examples for [example spreadsheets](https://github.com/MetaverseRPN-LLC/RPForge-Issue-Tracker/tree/master/csv_examples).

> rp!import \<datatype> [overwrite]

Available datatypes are:
### Items
[Example](https://github.com/MetaverseRPN-LLC/RPForge-Issue-Tracker/blob/master/csv_examples/item_example.csv)
Items require several columns:
  - name: A name for the item
  - description: A description for the item
  - image: The URL to an image
  - type: comma separated, valid values are `basic, nontransfer, unique, container, equippable, quest`, for example `nontransfer, unique, container`
  - capacity: If you specify the container attribute (premium only), you need to add a `capacity` column, with a number which gives the number of items which can be held in the container.


### Characters
[Example](https://github.com/MetaverseRPN-LLC/RPForge-Issue-Tracker/blob/master/csv_examples/character_example.csv)
Characters require several columns:
  - name: A name for the character
  - owner_id: The user id of the owner
  - pocket: Amount of money this character has in their pocket
  - bank: Amount of money this character has in their bank
  - description: A description for the character
  - picture: The URL to an image the character uses (optional)
  - prefix: The prefix you can use for the character instead of assuming (optional)
  - guild: The guild this character belongs to (optional)
  - guildrank: The Characters rank in the guild (required if guild)
 

### Recipes
[Example](https://github.com/MetaverseRPN-LLC/RPForge-Issue-Tracker/blob/master/csv_examples/recipe_example.csv)
Recipes require several columns:
  - name: A name for the recipe
  - ingredients: What the recipe needs to be crafted
  - product: What the recipe produces
  - time: How long it takes to make in seconds
  - hidden: If It should show up in the recipe list
  - method: The method someone has to enter to discover the recipe if its hidden


### Salaries
[Example](https://github.com/MetaverseRPN-LLC/RPForge-Issue-Tracker/blob/master/csv_examples/salary_example.csv)
Salaries require several columns:
  - role: The name for the salary
  - interval: How often the salary will be collectable (measured in minutes, must be 5 or greater)

Then they must also have at least one of:
  - money: How much money the salary gives
  - items: What items the salary gives

It can't be that the money amount is 0 and there are no items given.

And optionally:
  - type: Whether this salary is manual or automatic (defaults to automatic if this is left out. "m", "man", "manual", "a", "auto", and "automatic" (these are not case sensetive) are the valid values)

Also if you use rp!import salaries overwrite and you have salaries for roles that do not exit, the bot will create those roles for you.

### Shopitems
[Example](https://github.com/MetaverseRPN-LLC/RPForge-Issue-Tracker/blob/master/csv_examples/shopitems_example.csv)
Shops require several columns:
  - shop_name: The name of the shop this will be added to 
  - item_name: The name of the item that this adds
  - buy: The amount of money charged for buying this from the shop 
  - sell: The amount of money given for selling this to the shop 

# Scripting
	
The bot uses Lua for scripting, for a quick refresher on Lua syntax, see [here](https://learnxinyminutes.com/docs/lua/)

Some Basics:

# How to create a script
  - Write your code and save it in a .txt file
  - Upload the .txt file to your discord server, with the message !script luacreate scriptname
    Replace scriptname with the name you want to call the script.

	
## How to run a script
  To run a script you first need to create it.
  There are currently two ways to run scripts: when using an item, or when using an ability.

### Run a script when using an item
  - Create the item with rp!item create <itemname>
    Replace itemname with the name you want to call the item.
  - Use the Discord reactions to go through the menus, send messages to fill the menus with text.
  -	In step 4 (Types) of item creation, set its type to usable
  - Click next, this opens the menu Use.
  - Write the name of your script in this menu
  
  Now whenever someone uses the item with !use ITEMNAME , the script will be run.
  Remember this only works, if you actually have the item in your inventory. 
  To test the script you can give someone the item with !giveitem ITEMNAME 1 CHARACTERNAME
  
### Run a script when using an ability
  - Create the ability with rp!ability create name scriptname args
    Replace name with the name you want to call the ability
	Replace scriptname with the name of your script
	Replace args with the function arguments you want the ability to have.
	(These are variables you can reference in the script)
    Function arguments should be separated by newlines.
    Valid types: int, char, item, string, float
  Example
  ```
  rp!ability create Fireball fireball damage:int
  This creates the ability Fireball, running the script fireball, with a variable target(type int) defined
  ```

# Scripting Language

The bot uses Lua for scripting, for a quick refresher on Lua syntax, see [here](https://learnxinyminutes.com/docs/lua/)

## Builtin Functions
  There are a number of predefined functions that are available when your script runs, as well as several variables depending on the context in which the script runs.
  - get_inventory_count(charname: string, itemname: string) - Get the number of an item a user has in their inventory
  - get_item_attribute(charname: string, itemname: string, attrname: string, default: any = False) - Get the value of an attribute of an item, `default` is optionally added to set a value that is returned if the character doesn't have the attribute
  - set_item_attribute(charname: string, itemname: string, attrname: string, value: any) - Set the value of an attribute of an item
  - get_character_attribute(charname: string, attrname: string, default: any = False) - Get the value of an attribute of a character, `default` is optionally added to set a value that is returned if the character doesn't have the attribute
  - set_character_attribute(charname: string, attrname: string, value: any) - Set the value of an attribute of a character
  - display_item(itemname: string) - Show the details for an item with the given name
  - give_character_item(charname: string, itemname: string, amount: positive integer) - Set the value of an attribute of an item
  - take_character_item(charname: string, itemname: string, amount: positive integer) - Set the value of an attribute of an item
  - get_character_region(charname: string, default: any = False) - Get the region of a character, returning default if the character has no region
  - set_character_region(charname: string, regionname: string) - Set the region for a char
  - reply(message: string) - Send a message in the current channel
  - randint(floor: integer, ceiling: integer) - Generate a random integer between the floor and ceiling inclusive
  - choice(items: list) - Choose a random thing out of a list of things
  - choice(item1, item2, item3, ...) - Alternative way to use choice
  - asleep(time: float) - Wait a number of seconds (up to an hour) before continuing the code
  - give_role(charname: string, rolename: string) - Give a character (and its owner) a role with the given name
  - take_role(charname: string, rolename: string) - Take a role from a character (and its owner) with the given name
  - has_role(charname: string, rolename: string) - Returns True if the character has the role with the given name, otherwise False
  - give_pocket(charname: string, amount: float) - Put an amount of money into the character's pocket
  - take_pocket(charname: string, amount: float) - Take an amount of money from the character's pocket. Will return False if the character doesn't have enough
  - get_pocket(charname: string) - Get the amount of money a character has in their pocket
  - give_bank(charname: string, amount: float) - Put an amount of money into the character's bank
  - take_bank(charname: string, amount: float) - Take an amount of money from the character's bank. Will return False if the character doesn't have enough
  - get_bank(charname: string) - Get the amount of money a character has in their bank
  - get_character_region(charname: string, default: any = False) - Set the value of an attribute of a character, `default` is optionally added to set a value that is returned if the character doesn't have a region
  - set_character_region(charname: string, region: string) - Set the region of a character
  - set_global_var(name: string, value: any) - Set a global var that can be accessed between scripts with the given name and value
  - get_global_var(name: string) - Get a global var with the given name
  - get_character_names() - Get the names of all characters in a table
  - wipe_char_attrs(name: string) - wipe the attrs for a character

Example script:
  ```
	a = randint(1, 100)
	give_pocket(char, a) 
	moneytext = tostring(a)
	words = char .. " opens the huge bag and finds " .. moneytext  .. " dollars."
	reply(words)
  ```
Gives a the user 1-100 money.
Then the script creates a sentence and replies it in the chat.
 
Example script:
 ```
random_item = choice("sword","apple","car","banana","phone")
give_character_item(char, random_item, 1)
replytext = char .. " got a " .. random_item
display_item(picked_item)
  ```
This script randomly picks an item, gives it to a player and shows some information about the item.
  
# Builtin Variables

  Depending on where this script is run from (from item use or ability use), different variables will already be defined, which can be used in your script.
  If the variable is not set(because the script wasn't called from items or abilities), the default value is false.
  
  Run script from item:
  ```
  item - name of the used item as string
  amount - the number of items used at once
  ```
  Run script from ability:
  ```
  You have access to all the variables that you defined when creating the ability, 
  they will have the name you created them with (`target -> target` in the script).
  channelid - the ID of the channel the command was used in
  ```
  Variables you can always use:
  ```
  char - name of the character running the script as string
  ```
