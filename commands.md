---
layout: default
title: Commands
nav_order: 3
last_modified_date: 2020-09-30
---

# Commands
{: .no_toc }


A full categorized list of all commands you can use with ShpeeBot.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Fun

### 8ball

Ask a yes/no question and get a predefined answer set in the config.  
**Usage: `8ball [question]`**

## Moderation

### Ban/Unban

Ban hammer time.  
**Usage: `ban [user mention] [reason]`**  
  
Unban a user.  
**Usage: `unban [user ID] [reason]`**

### Force ban

Bans a user by user ID
**Usage: `forceban [user ID] [reason]`**

### Clear

Delete messages in a channel sent by a specific user or everyone.  
**Usage: `clear [number of messages]` or `clear [user mention] [number of messages]`**  
> Aliases: `delete`

### Create Invite

Creates an invite to the channel it is sent in. Add limits such as maximum uses and time following the example below.  
**Usage: `createinvite [uses]`** or `createinvite [uses] [time (s/m/h/d)]`

### Kick

Kick a user from user mention.  
**Usage: `kick [user mention] [reason]`**

### Lockdown

Lock a channel down for the set duration, be it in hours, minutes or seconds.  
**Usage: `lockdown [duration]`**  
  
__Release the lockdown early using `lockdown release` or `lockdown unlock`__  
  
> Aliases: `ld`

### Mute/Unmute

Mute a mentioned user.  
**Usage: `mute [user mention] [reason]`**  
  
Unmnute a mentioned user.  
**Usage: `unmute [user mention] [reason]`**  

### Pin

Pin a message. Default pins the message above if no message ID is given.  
**Usage: `pin [message ID]`**

### Reason

Update the reason for a specific ban, kick, mute, etc.  
**Usage: `reason [case number] [reason]`**

### Role

Add or remove a role from a user.  
**Usage: `role [add/remove] [user mention] [role name]`**

### Softban

Ban the mentioned user, clear their messages from the past two days, then unban the user.  
**Usage: `softban [@\user] [reason]`**

### Warn

Warn a user, send them a message, and save the warning to the mod-log channel.  
**Usage: `warn [user mention] [reason]`**

## System

### Help

Display information on all the available commands for your permission level or one specific command.  
**Usage: `help` or `help [command]`**
> Aliases: `h`, `halp`

### Exec 
Bot Owner Only
{: .label .label-red }

Execute a console command.  
**Usage: `exec [command]`**

### Info

Provide some bot info.  
**Usage: `info`**
> Aliases: `about`

### Loadcommand
{: .d-inline-block }

Bot Owner Only
{: .label .label-red }

Loads a new command without having to restart the bot
**Usage: `loadcommand [command name]`**

### Reload
{: .d-inline-block }

Bot Owner Only
{: .label .label-red }

Reload a command that has been modified without having to restart the bot.
**Usage: `reload [command]`**

### Settings
{: .d-inline-block }

Server Admin Only
{: .label .label-green }

View or change settings for your server.
**Usage Examples:**  
- `set`
- `set [get] [key]`
- `set [edit] [key] [value]`
- `set [add] [key] [value]`
- `set [del] [key]`

> Aliases: `setting`, `settings`, `conf`

### Stopbot
{: .d-inline-block }

Bot Owner Only
{: .label .label-red }

Stop the bot. (Or restarts the bot if you are hosting on a process manager)
**Usage: `stopbot`**
> Aliases: `restart`

## Utility

Todo

## Miscellaneous

Todo
