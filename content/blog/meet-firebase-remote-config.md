---
date: 2017-06-17
description: "Meet Firebase Remote Config"
featured: "1*RzxiNv3cFuyTzCiUj5Bgng.png"
featuredpath: "/images/blog/meet-firebase-remote-config/"
featuredalt: "Firebase Logo"
tags: ["firebase", "product management"]
title: "Firebase Hidden Gem for Product Managers"
type: "post"
---

I’ve been playing around with Google Firebase lately and to my surprise had found a real gem for product managers, but first —

## What is Google Firebase?

According to the website description it is “[**Google’s** mobile platform that helps you quickly develop high-quality apps and grow your business.”](https://www.google.co.il/url?sa=t&rct=j&q=&esrc=s&source=web&cd=14&cad=rja&uact=8&ved=0ahUKEwilnNfincXUAhUJlxQKHYOhC1MQFghwMA0&url=https%3A%2F%2Ffirebase.google.com%2F&usg=AFQjCNFaUSAeuiSoAtigecR5SNdxATwPKg&sig2=qqwYkW0BVm3SYIKWMCUbaA)

To make it short, it easier to think about Firebase as cloud for apps and websites. The app or web developer has set of basic yet very powerful services that allow him to write a full stack application without any need for backend coding.
To make it shorter, one developer can write a full production ready app in just few hours!

of course, this is limited to the most basic tasks like user authentication, analytics and simple storage of data; but for most POCs or apps relay mostly on frontend logic this is more than enough.
Furthermore, if it happens and your app is growing crazy fast, you don’t need to worry about scaling up or backend stability as everything based on google cloud infrastructure.

## You Said Product Managers…

Correct!
Firebase has a feature called [Remote Config](https://support.google.com/firebase/answer/6386651), this feature allows you to change parameters values directly from firebase console at runtime.
For comparison, a similar custom system will require you a backend developer, UI developer and a DBA not to mention the servers and infrastructure behind.

But if this wasn’t good enough, you can set different values to different audiences (AKA A\B Testing), and all of this with few lines implementation in the app code. 
That means the developer mentioned above, will be able to write a complete app WITH backend WITH production CMS system WITH A\B testing in just few hours — isn’t that amazing?

## Example Please!

Let’s take the following example, consider a fidget spinner app. As a product manager you want to control when to show an advertisement to the user.
Should it be after 1 minute of use? maybe 5? maybe 60?

So, in Firebase, all you need to do is to add a new parameter to dashboard called *timeTillAd:*

![](/images/blog/meet-firebase-remote-config/1*560D0DUeeBM5NT8jXCS7Fw.png)

The developer should take this parameter and implement its logic in the code. You should note that the API includes a default value in cases where the fetching of the value failed (like when there is no internet connection).

Once the app is live you can change this value, publish and immediately all apps in production will have the new logic. no need for complex DB scripts or apps resubmissions, isn’t that just amazing?

BTW — had you notice the *Add value for condition* link on the top right corner? This is the A\B testing included for free. Let’s give a better look inside:

![](/images/blog/meet-firebase-remote-config/1*L6rSLO3XY8SdnkKMQt12NA.png)

So, as you can see, you can provide a different value for a different app version or operation system (android green and iOS blue? why not!)
You can perform the traditional A\B testing through the “user in random percentile” and also provide a different value for different geo-location.
Since Firebase, as mentioned, also includes a very good analytic system; you can change and verify results all from the same place.

**Conclusion, Some Warnings and Additional Info**

As a product owner Firebase gives you exceptional strong tool to verify, test and change your app behavior. all from the same place with minimal coding effort from the developers.

I truly believe you should try it out. from my experience, it could save months of development cycles. 
Fast validation of assumptions is critical today to move fast in the constantly changing app world, and Firebase Remote Config is the kind of tools allowing you to do that.

**WARNINGS**!

1. Having the possibility to change your app logic from remote location means that if you choose invalid value you could easily crash all your apps in production.
If in our example you will put 90 in the value of *timeTillA*d but the app code support just until 60, you can’t expect the outcome.
So my strong advice is to communicate with the developer before about what the app logic will support and to have a stage project where you can test the values before changing production directly.

1. Remote Config, for some reason, takes good amount of time to initialize. so, if you count about dynamic values for your FTUE or app load, you should be aware it could take 10–20 seconds.
My advice here is to avoid that. don’t delay your FTUE for nothing, use constant values for loading parameters and Remote Config for runtime parameters.

**Additional Reading**

A very good iOS tutorial for Remote Config implementation you may find in [Ray Wenderlich](https://www.raywenderlich.com/143712/firebase-remote-config-tutorial-for-ios) site (which I highly recommend!)

Joe Birch wrote on Medium [in-depth review of Remote Config](https://medium.com/@hitherejoe/exploring-firebase-on-android-ios-remote-config-3e1407b088f6) (as part of general review of Firebase).

I will recommend reading both if you wish to better understand how to use this powerful tool.
