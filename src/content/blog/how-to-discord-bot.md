---
author: Devansh Kandpal
pubDatetime: 2024-10-31T22:42:00Z
title: How (and how not) to make better Discord bots
slug: how-to-discord-bot
featured: false
draft: true
tags:
  - discord_bot
description: Some tips on making improving the user experience of your Discord bots.
---

This is an example post just to get this blog up and running. It is a repost of an
[old article I had posted on dev.to](https://dev.to/deathvenom54/how-and-how-not-to-make-better-discord-bots-4172)
(its age must be apparent by the way I introduce slash commands :D). It's a great thing that the original was formatted
in markdown, which could be ported directly.

## Table of Contents

You clicked on this post, which probably means you too make bots, like me. Or you want to.
Before I get into this article, I want to clarify that this is not a guide,
but a bunch of ways in which you can improve your bots.

## Curb your prefix

It is very common among bot developers to come up with complex and unique command prefixes for
their bot, to perhaps stand out. While thinking of a prefix, keep mobile users in mind.

A simple symbol like `.`, `$`, `!` serves the purpose very well, and easy to locate on any
keyboard. A short word prefix (2-4 letters) is also a good idea.

Avoid having multiple symbols or a combination of letters and symbols. Some notable examples
are: `$!help`, `bot-name!help`. Better yet, use slash commands.

## Use slash commands

Slash commands are somewhat new to Discord and still evolving. I believe that they are the future
of bot interaction in Discord. Unless you have been living under a rock, you must have seen or used slash commands.

![Slash command menu](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/cf52fehv9t6inoy6ut4n.png)

By pressing `/`, you can see all the available commands for a bot, along with its description.
When you use a command, you can see all its parameters. And that's not all! You can even specify
what type each parameter should be, so that oblivious users don't enter a string in an integer type parameter.

However, every coin has two sides. slash commands need to be registered beforehand and handled according
to their `custom_id`, which makes it a tedious job to implement them. To solve this problem,
I wrote [djs-marshal](https://github.com/DeathVenom54/djs-marshal), check it out.

## Use Message Components

Similar to the point above, message components such as Buttons and Select Menus are a much better
way to take input from the user. Are you making the user send a particular reaction to make a
choice or to proceed? Toss that out and use buttons or select menus!.

![using reaction](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vu41syo4fdd94jveueeq.png)

![using message button](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/qpayn9a48a5bqmyr44r5.png)

## Make a help command

Unless your bot is meant to be used by a single person, you should try to add a help command to your bot.
This should give a brief description of what the bot does, list all the available commands of your bot,
as well as some related links like support server invite and bot invite.

**Pro tip #1:** Make the bot say something along the lines of `Use /help for help` when the bot is pinged.

**Pro tip #2:** Set the bot's description and activity to a message that includes its help command.
This way, no matter how a Discord user finds the bot, they will be able to get relevant information
about the bot without having to search it up.

![Example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8ekevzsc4uy48rhrqn17.png)

## Don't add vote-walls

A lot of bots block their commands behind a vote-wall. This means that you must vote for the bot
on some bot list in order to use it. Though it might bring you a lot of votes fast, it is not _the way_.
This may even trigger people to write negative reviews and use an alternative bot. By all means,
promote your bot by requesting users to vote for it, but forcing them to do so is not a good idea.
