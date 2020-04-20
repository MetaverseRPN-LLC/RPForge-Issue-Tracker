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

Now lets dive into the categories you have access to

- Description
   
   This is a little summary of your character, its not important for mechanics and entirely flavour
   
- Picture

    A link to a picture that will show up when someone looks at your character or you assume the character
    
- Prefix

    A prefix you can quickly use to talk as the character or use a command as them (you can skip the default prefix if youre using this)
    
    
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

##### Description
- Flavour text, no mechanical impact

##### Picture
- A link to an image that shows up when someone looks up the item

##### Type
- several tags you can add for unique effects, the bot explains the tags in the creation prompt

## Economy

> Note:
>
> You need a character to use or be targeted by these commands as only characters can have money or inventories

### Balance

> rp!balance

Lets you check how much money you have in your pockets and in your bank, if you just made your character you probably have nothing on there or the starter amount. If you don't have a character use this it just wont work at all


### Givemoney (Mod)

> rp!givemoney \<amount> [targets...]

You will likely need this money command a lot while setting up as it allows you to create money out of thin air and give it to the specified character/characters


