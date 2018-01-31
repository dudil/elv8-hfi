---
title: "Messaging Platform for Game Developers — Part 2"
description: "Discord — The Rising Star of Players Communication"
date: 2017-10-20
image: "/images/post/Messaging_Opportunities_2/1*S9CzrBzmvETEy44egVY4IQ.png"
tags: ["Bots", "Gaming", "eSport", "Game Development", "Facebook Messenger"]
categories:  ["Technology"]
---

On my previous post, [Messaging Platform Opportunities for Game Developers](/post/messaging_opportunities_1/) I went through *why* players communication is essential for your game, *what* solutions exist today and *how* to use the Facebook Messenger platform to deliver a great extension of your game to your players.

While the Facebook Messenger is great and easy to implement solution, it has one major disadvantage (as for the moment). You can have your game extended ***on the Messenger platform*** but you can’t have the Messenger platform ***integrated into your game***.

So while your players can enjoy this truly amazing platform to communicate and share, when they are in your game they will have to use either your in-game communication solution or just open the two apps at the same time (which will consume much more bandwidth / CPU / battery)

In this post, I will introduce you to the Discord app and to Discord GameBridge. A potential game-changer for game developers that you should definitely start looking at.

![](/images/post/Messaging_Opportunities_2/1*K6LxEi2m-_nyVGFUlK-4tA.png)

## About Discord

[Discord](https://discordapp.com) is a communication platform very much similar to Slack and Workplace by Facebook. While the later ones are aimed at changing the way organizations are working, Discord main focus is players communication.

It has dark UX and game-related media, unique gamers jargon (Team communication space is called *Server*, your user ID is called *IGN* etc.) and integration with major games and streaming platforms.

Discord founded in 2013 as game development startup (Their game called “Fates Forever”). The game was not able to track too many players attention so in 2015 they pivoted into the players communication space. No surprise the platform is so much connected with its target audience.

According to [TechCrunch](https://techcrunch.com/2017/06/07/discord/) Discord lately raised estimated $50M at a pre-money valuation of $725M from VCs like Greylock, Benchmark, and Tencent. Discord platform has 9M unique users per day and growing.

In their own words — they are here to stay.

If you are not familiar with the platform and still making games targeting communities/guilds, stop everything and do it now.

### The Discord Platform

The Discord app is completely multi-platform. There are iOS / Android / Web / PC / Mac dedicated clients. This allows player to communicate from everywhere anytime. The PC client also supports overlaying over some popular games, so players can use the client to communicate and coordinate with each other during game.

On the platform itself, you are able to post, chat, use voice chat rooms and even video chat groups that are rolling at the moment. If you look at the comparison page provided on the platform, you will notice Discord is all about low performance impact communication.

![](/images/post/Messaging_Opportunities_2/1*K2szRuMmXZrBEbNubWyVfw.png)

This is no accident. Knowing well their audience, The team at Discord understand there is nothing more frustrating than lagging and slow performance because of some extension you just added to the game.

![](/images/post/Messaging_Opportunities_2/1*bvyclvD4FW5IfvGnWq6phA.png)

Read [here](https://discordapp.com/features) for the complete features list. You will find it complete, high graded and in some case (IMHO) a good alternative to Slack and Workspace.

Discord is in use for everything from setting up and recruiting esport teams to development of games, community tools, casual talk etc.

*Consider that if you are developing games and looking for a team communication platform which is free and has decent feature set (Yep they have Github bots)*

## Discord for Game Developers

Discord is unique in my view compared to the other platforms.

They have a vast set of API and they are quite open for external developers. Adding the fact that their target audience is more technical and DIY in mindset, you can find vast Bots & Apps that truly makes the platform rich and fun.

For the game developers, this is great opportunity to provide extensive environment inside Discord for their communities. By providing APIs (or Apps), your game could largely extend into the platform. This is similar to what you can do on the Messenger Platform, but since Discord is much more *”complete”* in term of communication platform it has much bigger impact. For example, you can provide bots for groups and in voice chats rooms.

Furthermore, with GameBridge Discord allows you to extend your in-game communication with their own feature sets. This is a fresh change that allows you to use external platform to extend **your game** rather your game **extend the platform**

## Discord Apps

To start working with Discord I suggest creating an app that will extend your game communities on the Discord platform.

Go [here](https://discordapp.com/developers/docs/reference) for the complete API reference. There are also some good wrappers for your choice of programming platform, for example this python library.

While I won’t cover the API list, I would advice again (as did in [part 1](/post/messaging_opportunities_1/)) about the recommended architecture and deployment.

![](/images/post/Messaging_Opportunities_2/1*oLH4fXIP3lLLK30hipAAsg.png)

I strongly advise you will not connect directly from your game platform into the Discord platform. Instead, create a set of APIs that by exposing to Micro-services will allow you to:

1. Utilize and use on other platforms like the Messenger platform

1. Expose to DIY coders which are part of your players community

## Discord GameBridge

GameBridge (Still in Beta) is a great opportunity for game developers to enhance in-game communication in their game using Discord.

Remembering that Discord is focusing on user experience and low latency is a good guarantee that your game is not highly affected by this integration.

![](/images/post/Messaging_Opportunities_2/1*irvm2qlX7tQ-8nFNzqgGIw.png)

Read [here](https://discordapp.com/gamebridge) more about it.

**Please note to the followings!**

1. The Service is in Closed Beta

1. It is available only for Desktop Games

1. The SDK is only for PC games (via dll)
You can use it on Mac (but with [RPC](https://discordapp.com/developers/docs/topics/rpc))

If you are in the space of Desktop multiplayer games, it is good starting point to try it out.

If you just want to experiment, you should probably start with the RPC version as it is less intrusive for your game and easier to turn off where needed. Just note that the RPC will only work with players already have the Discord client installed on their Desktop.

## Notable Disadvantages

Since Discord is all about the players, it has some considerable disadvantages comparing to other platforms (e.g. Facebook Messenger)

1. GameBridge is still in beta and only supports desktop games. So if you are on the mobile field this is out of reach at the moment.

1. It is not designed for the casual players. Same as you won’t use Slack to organize family dinners with grandma. The casual player will find this platform complex and unintuitive to use.

1. Discord is (at the moment) all about the players and not about game developers. They won’t charge you for using their platform but they do charge their players for [premium (AKA Nitro) accounts](https://discordapp.com/nitro). So don’t expect 24/7 support or dedicated accounts managers. Saying that, with the introduction of GameBridge that probably will change in the future.

1. The user base is limited in comparison to other platforms (90M vs. 2B). They also don’t offer any decent tools for discovery. That means that you have no viral distribution and new players discovery — so you should rethink your efforts and priorities.

1. You are extremely limited with user info. All you may get is the player email. (No retargeting and Lookalike here…)

1. You don’t have any analytics about usage, flow etc. Of course, you can always use your own internal solution, but that will make integration more complex.

![](/images/post/Messaging_Opportunities_2/1*N9ic-IeGu2YXpXSGqix36A.png)

## Ok I Got your point…

Yep, Discord is not the perfect solution for game developers. **BUT**, it is very good in what it is specialized about. Hardcore gamers communication platform.

So as always, you should consider the pros and cons and decide which solution fits you better.

Are you doing casual mobile game aiming for large distribution? Go with the Messenger Platform, it has all the cool features you need to grow your game

Are you aiming to esport or hardcore desktop gamers? Discord is the answer for you and you should focus your effort on growing your community there.

In between? not sure? well…

![](/images/post/Messaging_Opportunities_2/1*2swN-wPdQQPKZEhI2NohkA.png)

Keep an eye over Discord — it is evolving fast and here to change the game.

The good point is that if you stick around with the proposed architecture and micro-services deployment, doing both is **absolutely doable**!
