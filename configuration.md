---
layout: default
title: Configuration
nav_order: 3
last_modified_date: 2020-09-29
---

# Configuration
{: .no_toc }


ShpeeBot requires an initial configuration before startup.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


See the example config file [config.js.example](https://github.com/LeoDoesThings/ShpeeBot/tree/master/config.js.example) as an example.


## Owner ID

```js
// Bot Owner, level 10 by default. A User ID. Should never be anything else than the bot owner's ID.
  "ownerID": "123456789"
```

**You can get your Discord User ID from right clicking your profile with developer mode enabled.**

--

You can also get your ID from backslash mentioning yourself;  
```
e.g.        \@ShpeeBot
Will say:   <@337009470666440704>
```
Make sure you paste in the numbers only, not including the `<`, `@`, or `>`.

## Bot Admins/Support

```js
// Bot Admins, level 9 by default. Array of user ID strings.
  "admins": [],

// Bot Support, level 8 by default. Array of user ID strings
  "support": [],
```
See the Owner ID section for methods on getting User IDs

ShpeeBot uses an internal permissions system to prevent normal server users from executing administrator level commands.
"Bot Admins" users will have the same permissions the Bot Owner has, but will have limited access to commands like reloading the bot or bot commands.  
"Bot Support" users will have the equivalent of server owner access to any server with ShpeeBot in it. Like the name says, these users should only have these permissions to support the server owner in troubleshooting the bot.

## Bot Token

```js
// Your Bot's Token. Available on https://discord.com/developers/applications/me
  "token": "mfa.VkO_2G4Qv3T--NO--lWetW_tjND--TOKEN--QFTm6YGtzq9PH--4U--tG0",
```

Go to <https://discord.com/developers/applications/me> to get your bot token.  
***NEVER SHARE YOUR BOT TOKEN WITH ANYONE ELSE.***

## Intents

```js
// Intents the bot needs.
   intents: ["DIRECT_MESSAGES", "GUILDS", "GUILD_MESSAGES", "GUILD_MESSAGE_REACTIONS", "GUILD_INVITES", "GUILD_BANS"],
```

For join messages to work you need Guild Members, which is privileged and requires extra setup.
For more info about intents see: https://discordjs.guide/popular-topics/intents.html#enabling-intents

## Bot Status

```js
// Bot status [online / idle / invisible / dnd]
   status: "online",

// Bot status type [PLAYING / STREAMING / LISTENING / WATCHING]
   statusType: "PLAYING",

// The game you want the bot to play. Leave blank to disable
   playingGame: "{{prefix}}help | {{guilds}} guilds | v{{version}}",
```
Set the bot status with these settings.
- "Bot status" can only be either `online`, `idle`, `invisible`, or `dnd` (do not disturb).
- "Bot status type" can only be either `PLAYING`, `STREAMING`, `LISTENING`, or `WATCHING`.
- "playingGame" sets what game the bot will be playing. 
  - `{{prefix}}` will be replaced with the default bot prefix
  - `{{guilds}}` will be replaced with the number of servers the bot is in
  - `{{version}}` will be replaced with the bot version specificed in `package.json`

## Google API Token

```js
// Used for music commands. You need to have these APIs enabled.
   googleAPIToken: "AIzaSyDSci1sdlWQOWNVj1vlXxxxxxbk0oWMEzM",
```

- Go to Google Console and log in.
- Create a new project (name does not matter).
- Once the project is created, go into Library
- Under the YouTube APIs section, enable YouTube Data API
- On the left tab, access Credentials,
- Click Create Credentials button,
- Click on API Key
- A new window will appear with your Google API key
  NOTE: You don't really need to click on RESTRICT KEY, just click on CLOSE when you are done.
- Copy the key.
- Replace the placeholder API token with your token in your config file.

## Default Settings

Default per-server settings. All new guilds have these settings.  
DO NOT LEAVE ANY OF THESE BLANK, AS YOU WILL NOT BE ABLE TO UPDATE THEM VIA COMMANDS IN THE GUILD.  

```js
defaultSettings: {
    prefix: ".",
    modLogChannel: "mod-log",
    modRole: "Moderator",
    adminRole: "Admin",
    systemNotice: "true", // This gives a notice when a user tries to run a command that they do not have permission to use.
    welcomeChannel: "welcome",
    welcomeMessage:
      "Say hello to {{user}}, everyone! We all need a warm welcome sometimes :D",
    welcomeEnabled: "false",
    swearFilter: "false",
    swearWords: ["fuck, shit, bitch"], // An array of swear words. These should be lowercase. (of course, I have not included much for certain reasons...)
    logCommandUsage: "true",
    sendHelp: "dm" // Available options: channel, dm
  },
```
These are all pretty self-explanatory.

## Audit Log

```js
auditSettings: {
  logMemberAdd: "false",
  logMemberRemove: "false",
  logDeletes: "false",
  logCommandUsage: "false",
  logBans: "false"
},
```
These are all turned off by default so guild owners can personalise these settings to their own liking for their server.  
These settings can be changed per-server through the dashboard.

## Dashboard

```js
  dashboard: {
    // Enable or disable the dashboard with "true" or "false"
    enabled: "true",

    // Your bots client secret. Available on https://discord.com/developers/applications/me
    oauthSecret: "",

    // HTTPS: 'true' for true, 'false' for false. Preferably set this to true for obvious reaons.
    secure: "true",

    // Randomly generate a number to use as a session secret
    // A session secret is used to encrypt cookies, so you want this to be something that can't be guessed easily
    sessionSecret: Math.random(),

    // Domain name (with port if not running behind proxy running on port 80). Example: 'dashboard.bot-website.com' OR 'localhost:33445'
    domain: "dash.website.com",

    // The port the dashboard will run on
    port: "3000",

    // The permissions the bot will need on the server.
    // For more info see: https://finitereality.github.io/permissions-calculator/?v=536079575
    invitePerm: "536079575",

    // Whether or not to require a login to see bot statistics
    protectStats: "true",

    // This information will be shown on the Terms and Privacy pages
    // You'll want to fill these in if you don't want any legal issues...
    legalTemplates: {
      // This email will be used in the legal page of the dashboard if someone needs to contact you for any reason regarding this page
      contactEmail: "name@website.com",
      // Change this if you update the `TERMS.md` or `PRIVACY.md` files in `dashboard/public/`
      lastEdited: "26 October 2020"
    }
  },
```

You can disable the dashboard completely by setting `enabled: "false"`

If you're planning on using ShpeeBot on multiple servers, use the dashboard to create per-server settings.  
**Fill in the legal section. You don't want legal issues do you?**  

## Rename file
Finally, you can rename `config.js.example` to `config.js` if you haven't already.
