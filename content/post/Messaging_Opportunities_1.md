---
date: 2017-09-14
description: "How to extend your community page and boost your game communities using the Messenger platform API"
image: "/images/post/Messaging_Opportunities_1/1*Kbi4dSS0tufV-Lvb_0gRhQ.png"
tags: ["Bots", "Gaming", "eSport", "Game Development", "Facebook Messenger"]
title: "Messaging Platform Opportunities for Game Developers"
category: ["Product"]
---
### Intro

Most successful games hold communities of people who enjoy playing them. Communities could be about anything: playing together, sharing achievements and experiences, live streaming of the game or holding special cosplay parties. The fact is that we, as human beings, enjoy sharing our gaming interest with fellow players.

For the game developers, these communities hold many advantages such as:

* **Better stickiness**, players are coming back to play and compete with friends.
This result with higher LTV and better retention

* **Increase engagement** around special community events and physical meet-ups

* **Viral Distribution** of the Game (and for the game publisher — lower costs of UA)

* **Games Discovery** by new audiences of gamers watching live streams (via Facebook/Twitch/Youtube) or offline play (like with Pokémon Go)

For eSport titles and Clan/Guild based games, strong* *communities are the cornerstone of their game, as they provide the most vital element of it.

![](/images/post/Messaging_Opportunities_1/1*RkRMgoP6QtK5h6vBo4g_MA.jpg)

### What tools are used to create and build communities?

![There are more](/images/post/Messaging_Opportunities_1/1*cNfY8upK34nkvjFuBigg6A.png)*There are more*

As seen on the list, there are plenty of different options for players to create, build and grow game communities. Still, for game developers, the main platform to create communities is the **in-game** communication.

### In-Game Communication

In-game communication is the way players interact with each other inside games. In-game communication is a vital part of any multiplayer game. You will find out that beginners and occasional players will tend to use and rely solely on your in-game platform. This is usually how communities are built; people play and communicate with each other inside the game.

![Try to track that message from last week](/images/post/Messaging_Opportunities_1/1*byY9xtfDdk43F8PjE6CmEg.png)*Try to track that message from last week*

However, it is rare to see game developers building in-game communication as the top in class messaging platforms. For the same rich set of features, in-game communication platforms need to support:

* private & group chats

* Chat rooms management

* Multilingual support

* Sending and sharing videos and images

* Voice and Video calls (also for groups)

* Security and Chat Policy active enforcement

![I hope he got my message right](/images/post/Messaging_Opportunities_1/1*oiJ1ecQ8LKojQ34lN325gQ.png)*I hope he got my message right*

Development and maintenance of such features in-game are complex with low ROI in compare to alternative features. Therefore, it makes sense most game developers choose to have only the basic features of in-game communication

### Community-Used External Platforms

As the game grows in popularity and as guilds play a major part in your game, players tend to look for and use external tools to communicate and interact.

While this growth is great for any game, developers should mind a few downsides:

1. Inability to influence on published content or players abuse

1. Loss of valuable data about players behavior outside the game ecosystem

1. Lack of means to reach out to new players and new audiences

### Facebook Community Page

The Facebook community page is mandatory for any game looking to advertise and grow using the FB platform. Most game developers already use the community page to interact with their players in term of support, events, sales, and special announcements.

A community page is also a place where players can voice themselves, publish fan content and interact with each other.

In terms of analytical data, you have a full view of players interaction and engagement with your page posts, which you can also pull via API to include with your other data sources.

You can also combine players analytics inside and outside the game ecosystem if the game makes use of the Facebook login API.

### Create a Smart Community Page with Facebook Messenger Platform

![](/images/post/Messaging_Opportunities_1/1*SvZBwwxdYxrLgavikXEkcA.jpg)

For game developers, the Messenger platform is an amazing opportunity to enhance the Facebook community page.

The Messenger platform has:

* Enormous potential of 1.2B users

* Easy to use and intuitive UX for all around players (casual to hard core)

* Vast amount of discovery tools (Barcode, invites, direct link etc.)

* Growing set of APIs for developers to integrate with

* Various ways for multi-platform communication (chats, groups, calls, video calls)

The Messenger platform API is based on your FB community page. This allows you to quickly integrate and grow your game community. Consider the following set of features you have at your disposal:

* Create a chat bot as an added way to interact with your players

* Get players data to get more insight about your game audience

* Chat extensions for custom web-views to use inside chat& group chat windows

* Built in analytics to view platform KPIs

* Payments API for selling physical merchandise

* Built in NLP for more natural interaction with players

* Messenger game to extend your players game experience

In few short few steps, you will be able to set up a simple bot to interact with your players. Following more APIs integration, you will be able to harness the full potential of the Messenger platform!

![](/images/post/Messaging_Opportunities_1/1*AhNuxvINYO1gPg4wjqrIbA.png)

### Before we Start — Recommended Architecture

I highly recommend you externalize your game APIs. This will allow you to decouple the API integration from your game infrastructure.

The basic architecture of using the Messenger platform involves setting up Web-hooks. This is an idle setting for [Micro-services](https://en.wikipedia.org/wiki/Microservices) design.

Micro-services design helps you with rapid development and test of implementation. It allows you to add new features and update existing ones quickly without breaking other components. It also allows you to use Serverless architecture and platforms. Using [Serverless](https://martinfowler.com/articles/serverless.html) platforms, you can scale up automatically and cost-effectively without the need to set up a dedicated or new production environment.

![](/images/post/Messaging_Opportunities_1//1*R9lnOvTtRPDsDWn5JzhfGQ.jpg)

### First Step — setup your Messenger app

At first, you will need to create a new Messenger app that will connect to your FB community page. Following this step, you get an authentication token which you can further use to call and listen to other APIs.

This [official guide](https://developers.facebook.com/docs/messenger-platform/guides/quick-start) describes the steps required to create a node.js bot.
If you are more a Python guy (like me), [this excellent guide](https://github.com/jeanmidevacc/messenger-bot-python-flask-zappa-amazon) will instruct you how to set up a Serverless bot on AWS Lambda using the [Zappa](https://www.zappa.io/) framework in less than 20 minutes!

### Receive and Send Messages to Your Players — The Messages API

[https://developers.facebook.com/docs/messenger-platform/Webhook](https://developers.facebook.com/docs/messenger-platform/webhook)

The most straightforward action you are going to perform is automating your chat with your page players, AKA creating a chat bot. Creating chat bot will allow your bot to communicate freely with players. And this should be the first goal of implementing a community bot

![](/images/post/Messaging_Opportunities_1/1*OMmJBDc_K8hJam60BociVg.png)

Some implementation ideas:

1. **In-game Information** — player status, league, last challenge result.

1. **Support** — open support ticket, get status for a ticket, receive updates for global issues like maintenance etc.

1. **Guilds** — see player guild members’ FB profiles and connect with them through Messenger.

1. **Interactive help** guide, chat based tutorial for different sections of your game

### Learn more about your players — The User Profile API
[**User Profile API - Messenger Platform - Documentation - Facebook for Developers**](https://developers.facebook.com/docs/messenger-platform/user-profile)

Using the user profile API, you will be able to retrieve basic information about the player interacting with your bot. Having the user profile, you will be able to get:

* Better insights about your players

* Connect the profile to your in-game entity, offering better chat personalization

* Build and optimize your lookalike and retargeting groups

* With Facebook login, you have a full view of players activity. Also, when players are communicating about the game outside the game.

### Visual interaction in group messaging — Chat Extensions
[**Chat Extensions (NEW!) - Messenger Platform - Documentation - Facebook for Developers**](https://developers.facebook.com/docs/messenger-platform/guides/chat-extensions)

Chat Extensions is a new feature for the messaging platform just announced on [the last F8 conference](https://chatbotsmagazine.com/live-from-f8-group-bots-with-messenger-chat-extensions-641a3d66b367). Chat Extensions lets bots provide interactive, social features that users can invoke directly into their conversations.

Since Chat Extensions are actually Webviews, there is almost no limit to the type of content you can share with the player.

Some examples of using chat extensions could be:

* View leaderboards of the game

* Show and share player profile (Rank / special skins etc.)

* See special events / offers / sales

The most exciting part of Chat Extensions is that they enable developers to add app content to chat groups. I like to think about it as a “chat groups live AI assistance”.

For community-based games, this should be a MANDATORY implementation! 
Chat Extensions allow players to interact/share in a group directly with an in-game content.

Think about the following scenarios:

* Players in chat group start group queue together (making matching easy, friendly and intuitive)

* Players share reply of the last match and discuss it on the guild group chat

* Players setup practice game for new guild recruiters

* Players review the state of the group challenge and able to track and discuss it

Each one of the ideas above needs intense efforts to implement as an in-game feature. But, with the power of the Messenger platform, you will soon be able to create top of class game extensions with minimal effort.

Furthermore, you get the profiles of users interacting with your Chat Extension even if they are not registered with your community page.

Having this users’ profiles makes it easier for you to interact with them on the FB platform and gain extend analytic about the true outside game activity of your players.

### Get Data Relevant for Chat Activity — Analytics & Messaging Insights API
[**Analytics - Messenger Platform - Documentation - Facebook for Developers**](https://developers.facebook.com/docs/messenger-platform/product-overview/analytics)

Having a complete game analytics is a key factor for any successful game. You use analytics to better understand players journey inside your game. To recognize the most likable and played features and note the ones in need for an improvement. Same goes with out-of-game analytics: you can track your advertisement spent and performance and your community activity.

Using the Analytics tools and messaging insights API you can get deeper insights and understanding for your player’s interaction with the community outside your game platform.

Questions like:

* Are my players interacting with each other?

* Do they spend more time in-game playing or outside the game planning their next move?

* What is their engagement for special offers and special events in term of group discussion?

* What information are they looking for in the page/bot?

### Advanced — Sell game merchandise using the Payments API
[**Payments (Beta) - Messenger Platform - Documentation - Facebook for Developers**](https://developers.facebook.com/docs/messenger-platform/payments)

Selling your own game merchandise such as tee-shirts and action figures is a peachy way to engage players, and monetize further your game IP.

Using the Messenger platform payments API, directly selling these items to your players is even easier than before. You could implement “buy now” button or show a custom Webview.

There are few options in which you can implement an in-chat store. I recommend reading this [guide](https://developers.facebook.com/docs/messenger-platform/payments) to understand the different ways in terms of availability and prerequisites.

### Advanced — Humanize your bot interaction using Messenger built-in NLP
[**Built-in NLP - Messenger Platform - Documentation - Facebook for Developers**](https://developers.facebook.com/docs/messenger-platform/built-in-nlp)

NLP (Stands for *Natural Language Processing*) allows your bot to “understand” complex sentences and to respond accordingly. While this feature is still in its basic, it holds a great promise to make chatting with bots more human and natural for your players.

At the moment, the Messenger platform built-in NLP detects Greetings, Thanks and Bye and data such as date, time amount of money, phone numbers and emails. This should be enough for you to start experimenting.

I suggest starting experiment with NLP so you can understand how it works and how to code it. Once you feel more comfortable using NLP, you can move to use external NLP services like [Wit.ai](https://wit.ai/) or [Api.ai](https://api.ai/)

### Advanced — Create your own HTML5 game for the messenger platform (Closed Beta)
[**Instant Games Now Available on Messenger and Facebook News Feed - Facebook for Developers**](https://developers.facebook.com/blog/post/2016/11/30/instant-games-closed-beta/)

If you wish to leverage the Messenger platform reach and instant collaboration nature, consider developing an extension or even a new game that runs directly on the Messenger platform.

Games running on the Messenger platform are social and instant by nature. They let players interact and play together. There are some great examples like Zynga’s “Word with Friends”.

![I’m loosing…](/images/post/Messaging_Opportunities_1/1*nTwlnhzvUzGVrMoXXm50Hw.png)*I’m loosing…*

To be able to publish your game on the Messenger platform you first need to create an *instant game*, which is currently a closed beta.

If you think your game fits the concept and wish to participate in the beta program, register through this [link](https://www.facebook.com/help/contact/173350173135692).
