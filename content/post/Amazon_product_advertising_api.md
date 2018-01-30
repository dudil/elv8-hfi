---
title: "Amazon Product Advertising API"
description: "What is It Good For? How to Use It? And Why It Could Put You at High Risk?"
date: 2017-08-08
image: "/images/post/Amazon_product_advertising_api/1*ss6S2jY2t8L87ME9TzSukA.jpg"
tags: ["aws"]
categories:  ["Technology"]

---
## TL;DR

The Amazon Product API is a great tool for websites and apps publishers. The API allows a publisher to search, present and share relevant products on the Amazon website. Getting extra money for purchases done by their users on Amazon.

To use the Amazon product API you are required to create an access key. This access key is used to sign all calls to the product catalog. This means chances are you are using this key in your app \ website out in the open.
If you will follow the exact procedure created by Amazon and will fail to put attention to details you are actually using the root access key of your aws account!

In the following article, I will explain about the Amazon Product API and why you have to use these keys for the first place. 
Then I will explain what is the risk with root access keys and how to avoid this mistake.

## What is the amazon Product API?

![Amazon really nailed it this time with this logo!](/images/post/Amazon_product_advertising_api/1*9G0i8xqjixaV3AORRC1H_g.png)*Amazon realy nailed it this time with this logo!*

The Amazon product API is a tool for Amazon affiliates to search, show, share and finally direct traffic into specific products inside Amazon.
It is intended to use programmatically to allow affiliated websites \ apps to interact programmatically with the Amazon megastore.

![Note to self — switch to power saving led light bulb](/images/post/Amazon_product_advertising_api/1*aOK-fnQMxZezhqOQb3c7sQ.jpg)*Note to self — switch to power saving led light bulb*

let me set up a simple example to demonstrate that:
You operate a website named *LetThereBLight.com* a website dedicated to the wonders of light bulbs.

Enthusiastic users discussed and recommend each other for new types of light bulbs. maybe, right after reading these review they will go to amazon.com to look for them and buy them.

**Here is your monetization option!** Amazon will pay you if any of your avid readers will buy light bulbs from the website. But for this, first, you need to show them the exact link to the product.

However, as LetThereBLight.com is extremely popular. It is hard for you to track all different product mentioned and search them on Amazon and manually add the relevant links with specific details etc.

### Amazon Product API for the Rescue

You set-up a script on your website to recognize when a light bulb is mentioned. Once you have the right keyword all you have to do is call the search API, let us review the call:

    [https://webservices.amazon.com/onca/xml?
    **AWSAccessKeyId**={Your Access Key}&
    **AssociateTag**=letthereblight-20&
    **Keywords**=60w%20Edison%20ST58&
    **Operation**=ItemSearch&
    **ResponseGroup**=Large&
    **SearchIndex**=Tools&
    **Service**=AWSECommerceService&
    **Timestamp**={Call Time Stamp}&
    **Signature**={](http://webservices.amazon.com/onca/xml?AWSAccessKeyId=AKIAJNU6JEL3H5GNWRZQ&AssociateTag=letthereblight-20&Keywords=60w%20Edison%20ST58&Operation=ItemSearch&ResponseGroup=Images%2CItemAttributes%2COffers&SearchIndex=Tools&Service=AWSECommerceService&Timestamp=2017-08-06T11%3A21%3A47.000Z&Signature=LVkfJE6C8D9Yp0A9dKXgyYC00myUAyuhKAqzw55fK2Q%3D)Generated Signature}

This is the analysis of the call above:

* [https://webservices.amazon.com/onca/xml](https://webservices.amazon.com/onca/xml) — this is the API endpoint, it is different between amazon.com or amazon.uk and allow you to search in a specific store

* **AWSAccessKeyId** — and access key you generate to call and sign your request

* **AssociateTag** — a tag representing your site with Amazon. You have to use it if you wish to get paid by Amazon. Users that will get to Amazon with this tag will be set as users coming from your website/app

* **Keywords** — the keywords you were looking for, in this case, you were looking for a product similar to 60w Edison ST58

* **Operation** — you are stating you wish to search for product (there are other operation as well — not going to be discussed here)

* **ResponseGroup** — amount of details you wish to get back about the products. Large tells Amazon to include all data it has. You should consider what you actually need to optimize call time\bandwidth etc.

* **SearchIndex** — the category to search within (light bulbs are part of tools so we use that in our case). This, again, will filter unneeded results and will save time \ bandwidth. In our case, we wish to avoid light bulbs related to auto parts

* **Service** — kind of the same for all calls. you are indicating you are using Amazon Product API here

* **Timestamp** — the time you initiated the call to the API. It will make sure your call is “fresh”

* **Signature** — this is the hash key you get when you sign your request for the API. It is used to validate the call and it is related to the request signing process

The result you will get (rendered) should be something like this

![They are pricy — but will give you nice atmosphere](/images/post/Amazon_product_advertising_api/1*KWK2KmAg-3yviwCmhYpMwg.png)*They are pricy — but will give you nice atmosphere*

Amazing — isn’t that? showing this links in the bottom of the users’ reviews will allow readers to quickly find the item they just read about. And for you to get extra money from any purchase they might do on Amazon.

Here you can read more about the product API:
[https://affiliate-program.amazon.com/gp/advertising/api/detail/main.html](https://affiliate-program.amazon.com/gp/advertising/api/detail/main.html)

And about the request structure:
[http://docs.aws.amazon.com/AWSECommerceService/latest/DG/AnatomyOfaRESTRequest.html](http://docs.aws.amazon.com/AWSECommerceService/latest/DG/AnatomyOfaRESTRequest.html)

## The API Call Signing Process

Amazon is enforcing a signing process call *Signature Version 4:*
[https://docs.aws.amazon.com/general/latest/gr/signature-version-4.html](http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html)

> Signature Version 4 is the process to add authentication information to AWS requests. For security, most requests to AWS must be signed with an access key, which consists of an access key ID and secret access key.

Amazon is right here, the process does add security. But in the case of the Amazon Product API, this is mainly Amazon security. It is intended to control and stop massive unauthorized calls also known as DDOS attacks.
It is also intended to make sure nobody is using your tag in order to make fishy calls to the API, which will result in your account being suspended.

### Signing Process Explained (High Level)

To sign your request you need to:

1. Generate access key and key secret from an aws related account

1. Create a specific Amazon format timestamp each call (calls that are 5 minutes old will not be respected)

1. Order all the parameters in a specific order (A-Za-z)

1. Encode all the parameters in specific encoding format

1. Specific sign the call string using the access key and key secret you generated — result with *Signature* hash code

1. send the request with the hash code

To authenticate the call Amazon is doing the same signing process as you did. If the result is the same hash code as in the Signature element the call is valid and respected — else an error returned.

Only the caller (you) and Amazon knows the secret key. That means that only the caller and Amazon are able to generate a valid Signature element. Making sure no one is duplicating your calls or replacing \ injecting elements along the way.

![Well -this is not how secret keys looks like but I guess you got the idea](/images/post/Amazon_product_advertising_api/1*6172uzutRSQ9Kq5LtGWiNw.jpg)*Well -this is not how secret keys looks like but I guess you got the idea*

Unfortunately, the signing process is not so simple task to implement. It has much more very specific details not described above. needles to say, any detail you miss or putting wrong will result in a wrong hash code.

The code itself was built for PHP (amazon web store platform). The result is that for other platforms it is messy with lots of specific modifications. You should be aware of that as an extra space or wrong encoding will result in failures to get any valid response.

## Generating the Access Key and the Key Secret

I am providing here the exact walkthrough from amazon docs, including my comments.
[http://docs.aws.amazon.com/AWSECommerceService/latest/DG/ViewingCredentials.html](http://docs.aws.amazon.com/AWSECommerceService/latest/DG/ViewingCredentials.html)

> When you register as a Product Advertising API developer, an AWS account is created for you, along with a pair of credentials: an access key ID and secret access key. You use these credentials to submit requests to the Product Advertising API. The following steps show how to retrieve your AWS root credentials.

* This is the case when **you don’t **have an aws account.
Amazon authentication is same for **all services**. That means you can login to the aws platform with the same credentials you are using to buy kitten litter box. That also means you probably signed with the same credentials to the product advertising API as you signed to the aws account.

![Kitten not included](/images/post/Amazon_product_advertising_api/1*ss6S2jY2t8L87ME9TzSukA.jpg)*Kitten not included*

> **To manage your AWS root credentials**

> 1. Sign in to [https://aws.amazon.com/](https://aws.amazon.com/) with your AWS account.
> 2. Choose your **Account Name**, and then choose **Security Credentials**.
> 3. A pop-up message appears. Choose **Continue to Security Credentials**.
> 4. Choose **Access Keys (Access Key ID and Secret Access Key)** to locate your access key ID. Under **Actions**, you can delete your access key ID or inactivate it temporarily.
> 5. You can view your access key ID, but not the secret access key from this page. If you lost or don’t remember your secret access key, you’ll need to create a new pair of credentials.
 a. On the same page, choose **Create New Access Key**, and then choose **Show Access Key** or**Download Key File** to retrieve the credentials.
 b. Save the access key information in a safe location

> **Important**

> Only you and AWS should know your secret access key. It is important to keep it confidential to protect your account. Never include it in your requests to AWS. Never email it to anyone. Do not share it outside your organization, even if an inquiry appears to come from AWS or Amazon.com. No one representing Amazon will ever ask you for your secret access key..

* This is fairly easy and will take only a few minutes to create. As mentioned, you can view or download the secret key only at this point. There is no way to retrieve it later on. The document also mentioned you should do everything to keep that key private. So no, emailing\texting it everywhere and putting it on GitHub is not a good idea.

There is also a side note included:

> **Note**

> As a best practice, use IAM user credentials to access the Product Advertising API. You can continue using your root credentials, but root credentials provide unlimited access to your AWS resources. An IAM user has permission to access only the services you specify. For more information, see [Becoming a Product Advertising API Developer](http://docs.aws.amazon.com/AWSECommerceService/latest/DG/becomingDev.html).

### How this doc should have been written instead

> **To manage your AWS root credentials**

> 1. Sign in to [https://aws.amazon.com/](https://aws.amazon.com/) with your AWS account.
> 2. Choose your **Account Name**, and then choose **Security Credentials**.
> 3. If there are any credentials there **DELETE THEM NOW!!!!
Never ever use root credentials!**
> 4. Follow this procedure instead (from step 7). Yes, it has a confusing, not related title. Yes, it is just a bunch of information we didn’t find a place for, but still, it is the right one:
[Becoming a Product Advertising API Developer](http://docs.aws.amazon.com/AWSECommerceService/latest/DG/becomingDev.html)

![](/images/post/Amazon_product_advertising_api/1*PA_5sxJJZkTAbG5Zq-ht-g.gif)

### How this could happened?

Until lately [it was impossible to use a dedicated IAM access key](https://tiny-bhaskara4603.on.getshifter.io/2017/04/17/amazon-product-advertising-api-is-now-available-for-iam-users/) to call the API. While this is completely wrong, in terms of the process this was the only process you could follow to get an access key.
Even if it was impossible for Amazon to do, at least they could make sure you are not using your aws account in order to set up an affiliate account.

Anyway, once it was changed, and a specific IAM access key could be used, they didn’t change the original doc but rather just added it to another doc. Why? God knows — but sometimes a badly maintained knowledge base could posses security risk no less than bad code deployed.

## What is the big issue with root access keys?

The root access keys allow anyone holding them to do ANYTHING in your aws account. This includes adding services, take your data etc. It is the equivalent of giving someone your username and password to the account.

But better read this sad stories instead:

* OneLogin passwords were stolen — because of access keys stolen:
[http://www.eweek.com/security/onelogin-password-manager-breach-enabled-by-stolen-aws-cloud-keys](http://www.eweek.com/security/onelogin-password-manager-breach-enabled-by-stolen-aws-cloud-keys)

* Two developers were charged thousands of dollars for Bitcoin mining bots deployed on their accounts — after forgetting to remove access keys from code published on GitHub 
1. [https://wptavern.com/ryan-hellyers-aws-nightmare-leaked-access-keys-result-in-a-6000-bill-overnight](https://wptavern.com/ryan-hellyers-aws-nightmare-leaked-access-keys-result-in-a-6000-bill-overnight)
2.[https://www.theregister.co.uk/2015/01/06/dev_blunder_shows_github_crawling_with_keyslurping_bots/](https://www.theregister.co.uk/2015/01/06/dev_blunder_shows_github_crawling_with_keyslurping_bots/)

* And on and on and on…
[**Investigating CloudTrail Logs**
*These nightmares are typical in an AWS breach. Would you know how to investigate them?*medium.com](https://medium.com/starting-up-security/investigating-cloudtrail-logs-c2ecdf578911)

![Don’t be this kitten! Delete your root access keys NOW!](/images/post/Amazon_product_advertising_api/1*uUbXynOUwmy_Kc9Weqqmxw.jpg)*Don’t be this kitten! Delete your root access keys NOW!*

## To sum it up

1. The Amazon API is a great tool for website\app publishers. it allows them to add relevant links and to monetize further from their traffic.

1. Make sure you understand how to implement the API calls, and give attention to the signing process to make sure your calls are valid.

1. Pay attention when you create the access key and the key secret. make sure to follow the correct procedure and that you are not using your root access key

Thank you for your time reading this article.
Feel free to share if you find it useful.
