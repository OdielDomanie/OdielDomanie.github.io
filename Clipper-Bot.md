---
layout: page
title: "Clipper Bot"
permalink: /callipper/
---

# Clipper Bot

Discord bot that helps you clip live streams!

The bot can create clip files from live streams and VODs and post it directly to Discord.

Supports optional slash commands.


## How to use

(If you are not using slash commands, you can use `__help` to get details of individual commands.)

From simple to advanced:

![image](https://user-images.githubusercontent.com/76059582/184143606-bad02fbf-aac2-4c48-a354-6515d42272eb.png)

`/c`  
Clip the last 10 seconds.

`/c 30`  
Clip the last 30 seconds.

`/c 2:00 40`  
Clip from 2 minutes ago with a duration of 40 seconds.

`/a` is the same as `/c`, but audio only.

![image](https://user-images.githubusercontent.com/76059582/184273390-f453b738-91d4-4e51-8d1c-d7bda64bc212.png)

![image](https://user-images.githubusercontent.com/76059582/184273230-3f2cabbc-1d96-44ec-8b1e-cb89b7068aed.png)


`/c-timestamp 30:00 1:00`  
Clip the timestamp. Stream URL is optional, and if you don't include it, the last stream in the channel is assumed.

![image](https://user-images.githubusercontent.com/76059582/184143916-80909a73-ef47-4ba5-a42a-e77d2928c097.png)

`/edit 1001232251218981234`
Add edit controls to a clip. The number is either the message id, or the link to the message. You can find either of them in the `...` menu at the upper right of a message on Discord.

`/ss`  Take a screenshot with anime-face detection.

## Setup (for mods)

![image](https://user-images.githubusercontent.com/76059582/184271732-4afc9ab5-5159-43b2-9265-2f77b8c94735.png)

Use `/register <channel_name>` to "register" a streamer channel to a text channel. "channel_name" can be the name of a Vtuber, or a channel url (for example, `register Selen` will register both Youtube and Twitch channels). The streams of the registered streamer channel can now be clipped in this particular text channel.

`/unregister` to undo the above. Note: If you are ever deleting a text channel or removing the bot from the server, please unregister all the channels first to make my life easier :)

![image](https://user-images.githubusercontent.com/76059582/184272444-63916180-a468-44b2-917b-a3804f5ef69e.png)

![image](https://user-images.githubusercontent.com/76059582/184274581-c0e3c7b2-e418-4248-99b2-5aa7f55cef09.png)

`/stream <channel url or stream url>` to enable clipping one particular stream. If you enter a channel, that channel's current or next stream will be enabled.

The Discord file size limit is 8 MB for unboosted, and 100 MB for boosted servers. If the clips exceed this size, the bot posts a *link* to a clip instead. This is disabled by default, so be sure to run `/allow-links True` once allow the bot to post links.

If something "yabe" happens on stream, or if a stream is "unarchived", and you don't want people to clip that stream, use `/block-stream <stream_url>` to block that particular stream from being clipped for the next 48 hours (probably enough time for the VOD to either be edited or privated.)

### Slash commands

By default, all commands are disabled except to the server admins, even if it doesn't appear so in the Discord menu (this is a Discord bug). You need to manually assign roles to the commands in the Discord GUI. `/c`, `/c-timestamp`, `/edit`, `/a`, `/ss` commands are for general use, while the __other commands should have more restricted permissions__.

#### Migrating

If the bot is already on the server, but it doesn't have slash commands, you need to re-invite the bot with the new invite link.

The permission system for legacy (non-slash) commands does **not** sync with the slash commands, so it is advised to **only enable slash commands or the legacy commands, and not the both type of commands at the same time**. You can disable legacy commands by simply removing the "View Channel (Read Messages)" permission from the bot.

### Legacy commands

Use `__help Admin` to explore the settings related commands.  
The permission system for legacy commands is too complicated (and buggy) that I can't explain how to use them here, it is better to just contact me (developer) and ask, or even better yet, use slash commands instead as those have a permission system built in.

### Adding to the server

You can contact me (Terlick#8575) at Discord if you want to add the bot to your server, or have any questions.
