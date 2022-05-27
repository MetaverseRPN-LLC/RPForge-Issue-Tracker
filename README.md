Visit the support server:

[Discord Server Invite](https://discord.gg/mXZg2mk)

![](https://discord.com/api/guilds/303307934774067210/embed.png)

[Invite the bot](https://discordapp.com/oauth2/authorize?client_id=673737213959208980&scope=bot&permissions=805596240)


# RPGBot-V2-Issue-Tracker
A Github page for storing public data for RPGBot and tracking issues

This repository is for recording and reporting issues with the bot, crowd sourced translations, and hosting the tutorial. If you'd like to contribute, please message Henry or open a pull request!

Hello and welcome to RPGBot!

Before we get started heres a general overview to give you an understanding of what this bot is and isn't:

## What RPGBot provides


- Characters
    - can have custom attributes
    - you can talk as
    - can have their own money and inventories
- Item system
    - custom items
    - optionally useable(WIP)
    - customizable craftingsystem
- Inventories
    - Lets you collect items
    - Containers
- Economy
    - economy
    - player trading(WIP)
- Crafting
- Guilds
    - Groups for your players to make
- Salary
    - regular money or item supply for players
- Shop
    - server shop
    - player market
- Chance
    - lotteries
    - dice
- Regions
- Settings
    - custom currency name
    - language settings
    - prefix customiation
    - command enabling/disabling
- Backup
    - item importing
    - getting data from v1
- Premium Features
- Dynamic Combat Script
    - [Placeholder]
   
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

Now that thats out of the way lets get into how to use those things






## Characters

Before most of the bot can be used you are going to need a character, to create one type

### Creation

rp!character create \<name>

A prompt will come up asking you to type in a number for the category you want to edit you can either do that or click the reaction arrow that points to the right to go through this process. When you feel like you're done you can finish the process with the green checkmark reaction

All of the below categories are optional. You can just hit the checkmark right away
Now lets dive into the categories you have access to

- Description
   
   This is a little summary of your character, its not important for mechanics and entirely flavour
   
- Picture

    A link to a picture that will show up when someone looks at your character or you assume the character
    
- Prefix

    A prefix you can quickly use to talk as the character or use a command as them (you can skip the default prefix if youre using this)

- Template

    This is in developement still, don't mind it
 
   
    
Now that you have made your character lets jump through the basic other usages

### Assume

> rp!character assume \<name>

You can use this to become your character in a manner of speaking, the bot can only do this if it has the Manage Messages and Manage Webhooks Permissions
to undo it you can use 

> rp!character unassume

While assumed your sent messages will be deleted and replaced by the bot saying it with your assumed character's image as profile picture and with the original content of your message

Most commands on this bot will require you to use them as a character, wether you use the assume command or the character prefix for that doesnt matter


### Edit

> rp!character edit \<name>

This command lets you edit already made characters

### Lookup

> rp!character \<name>

This lets you look up a character


## Items

> Small Note:
>
> You need a character to actually have access to an inventory

###Creation

> rp!item create \name

Before you can do anything with items you need to create at least one
All the below steps are optional

##### Description
- Flavour text, no mechanical impact

##### Picture
- A link to an image that shows up when someone looks up the item

##### Tags
- A tag you can apply to an item if you want to accept any of its kind for a crafting recipe, for example accepting green, red and yellow apples for a recipe by giving them all the apple tag and using apple in the crafting recipe input

##### Type
- several tags you can add for unique effects, the bot explains the tags in the creation prompt

Hit the green checkmark to finish the item creation process.


## Inventory

> rp!inventory

Lets you view your current character's inventory

### Giveitem (Mod)

> rp!giveitem \<itemname> \<amount> [targets...]

Give One type of item to the specified character(s) or all characters with a specific role(s)
example:
> rp!giveitem Banana 12 @Henry#8808 @terabix#0001

> rp!giveitem Banana 13 mycharacter character2

> rp!giveitem Banana 14 @Administrators @​everyone


### Giveitems (Mod)

> rp!giveitems \<items...> \<targets...>

Give multiple items to the specified character(s) or all characters with a specific role(s)
Syntax is itemxamount
for example 
> rp!giveitems Bananax12 "Big Applex15" @Henry#8808 @terabix#0001

> rp!giveitems Bananax13 Applex12 mycharacter character2

> rp!giveitems "Small Bananax14" Applex9 @Administrators @​everyone


### Takeitem (Mod)

> rp!takeitem \<itemname> \<amount> [targets...]

Take One type of item from the specified character(s) or all characters with a specific role(s)
example:
> rp!takeitem Banana 12 @Henry#8808 @terabix#0001

> rp!takeitem Banana 13 mycharacter character2


### Takeitems (Mod)

> rp!takeitems \<items...> \<targets...>

Take multiple items from the specified character(s) or all characters with a specific role(s)
Syntax is itemxamount
for example 
> rp!giveitems Bananax12 "Big Applex15" @Henry#8808 @terabix#0001

> rp!giveitems Bananax13 Applex12 mycharacter character2

> rp!giveitems "Small Bananax14" Applex9 @Administrators @​everyone


### Give

> rp!give \<items...> \<targets...>

Give a set of different items to multiple people for example giving 2 apples this way gives every target 2 apples each assuming you have enough

> rp!give Bananax5 Applex13 @Henry#8808

> rp!give Bananax6 Applex23 charname charname2


## Containers

> rp!containers

View the containers your character has in their inventory


### View

> rp!container \<id>

View a container's contents



## Economy

> Note:
>
> You need a character to use or be targeted by these commands as only characters can have money or inventories

### Balance

> rp!balance

Lets you check how much money you have in your pockets and in your bank, if you just made your character you probably have nothing on there or the starter amount. If you don't have a character use this it just wont work at all


### Givemoney (Mod)

> rp!givemoney \<amount> [targets...]

Lets you "Spawn in" money, meaning the targeted characters will get this money from nowhere

### Takemoney (Mod)

> rp!takemoney \<amount> [targets...]

Lets you void money, meaning that money taken away like this vanishes into nothing


### Pay

> rp!pay \<amount> \<target>

You need to be assumed for this command, this command subtracts money from your character and gives it to the target character


### Baltop

> rp!baltop

This displays the 10 richest characters on the server


### Bank commands

> rp!bank deposit \<amount>

Takes money from this character's pocket and puts it into the character's bank account

> rp!bank withdraw \<amount>

Takes money from this character's bank and puts it into the character's pocket
The lowest the bank can go in balance is 0


## Lotteries


> rp!lottery

Lets you see currently running lotteries


### Create (Mod)

> rp!lottery create \<name>

Create a new lottery, a prompt will show up to walk you through the process


### Delete (Mod)

> rp!lottery Delete \<name>

Delete a lottery that is currently running


### Join

> rp!lottery join \<name>

Join the lottery, you need to be assumed for this to work



## Shop

### Info

> rp!shop \<name>

View a specific shop


### List

> rp!shops

List all shops that are available in the channel you use it in


### Create (Admin)

> rp!shop create \<name>

Creates a new shop, a prompt will guide you through the rest of the process


### Edit (Admin)

> rp!shop edit \<name>

Edit the shop with the given name a prompt will guide you through the process


### Delete (Admin)

> rp!shop delete \<name>

Delete the shop with the given name

## Shop Item Commands

### Add (Admin)

> rp!shop additem \<shopname> \<itemname> \<buyvalue> \<sellvalue> [requires]

Use this command to add items to the shops after creating them
If the buy value is 0 the item cannot be bought from the shop, same for sell value
To make buying the item require having another item, you may specify the [requires] argument, which should target an item name.


### Remove (Mod)

> rp!shop removeitem \<shopname> \<itemname>

This command will remove an item from a shop


### Buy

> rp!shop buy \<shopname> \<itemname> \<amount>

Lets you buy items from a shop, you need to be assumed


### Sell

> rp!command \<shopname> \<itemname> \<quantity>

Lets you sell items to a shop, you need to be assumed

## Player Market


> rp!market

Shows you what players on the server currently have listed on the market


### Sell

> rp!market sell \<item> \<quantity> \<price>

This puts the item you select on sale, people can buy it on the market if you do this, you need to be assumed


### Buy

> rp!market buy \<listing_id>

Lets you buy an item from the market, the listing id is the number next to their offer in the market

