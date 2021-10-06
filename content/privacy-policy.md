+++
author = "Iacopo Moles"

date = 2020-08-22T22:00:00Z
tags = []
title = "Privacy Policy"
toc=true

+++
This blog doesn't collect analytics of any sort by it's own. The blog relies on third party services to work properly:

## GitHub Pages

I host this blog on GitHub Pages (hosted and controlled by Microsoft) which has its [own privacy policy](https://docs.github.com/en/github/site-policy/github-privacy-statement#github-pages).

Up until August 2020 they described it as follows:

> If you create a GitHub Pages website, it is your responsibility to post a privacy statement that accurately describes how you collect, use, and share personal information and other visitor information, and how you comply with applicable data privacy laws, rules, and regulations. _Please note that GitHub may collect User Personal Information from visitors to your GitHub Pages website, including logs of visitor IP addresses_, to comply with legal obligations, and to maintain the security and integrity of the Website and the Service.

## AMP

Another issue is given by AMP (hosted and controlled by Google), which is only used in the AMP version of the blog (it activates automatically if you arrive from external services that support it).  As specified on the footnote of [their website:](https://amp.dev/)

> The services available at cdn.ampproject.org are provided by Google and the respective privacy policy applies.

Up until August 2020 on Google's main website [their privacy policy](https://policies.google.com/privacy?hl=en) specified:

> ### Information we collect as you use our services
>
> #### Your apps, browsers & devices
>
> We collect information about the apps, browsers, and devices you use to access Google services, which helps us provide features like automatic product updates and dimming your screen if your battery runs low.
>
> _The information we collect includes unique identifiers, browser type and settings, device type and settings, operating system, mobile network information including carrier name and phone number, and application version number. We also collect information about the interaction of your apps, browsers, and devices with our services, including IP address, crash reports, system activity, and the date, time, and referrer URL of your request._
>
> We collect this information when a Google service on your device contacts our servers — for example, when you install an app from the Play Store or when a service checks for automatic updates. If you’re using an Android device with Google apps, your device periodically contacts Google servers to provide information about your device and connection to our services. This information includes things like your device type, carrier name, crash reports, and which apps you've installed.
>
> #### Your activity
>
> We collect information about your activity in our services, which we use to do things like recommend a YouTube video you might like. The activity information we collect may include:
>
> * Terms you search for
> * Videos you watch
> * Views and interactions with content and ads
> * Voice and audio information when you use audio features
> * Purchase activity
> * People with whom you communicate or share content
> * _Activity on third-party sites and apps that use our services_
> * Chrome browsing history you’ve synced with your Google Account
>
> If you use our services to make and receive calls or send and receive messages, we may collect telephony log information like your phone number, calling-party number, receiving-party number, forwarding numbers, time and date of calls and messages, duration of calls, routing information, and types of calls.
>
> You can visit your Google Account to find and manage activity information that’s saved in your account.

## Staticman + Heroku

To provide a comment section I use a combination of Staticman hosted on a free instance of Heroku. The comments are rendered with the page and they won't hit external websites. When sending a comment you will include a mail (it's not checked and won't be used to contact you but is used as a precaution to prevent abuse) and it will be stored as a MD5 hash for unique identification. When sending the comment your request is redirected to an external hosting service that will handle the inclusion of your comment on the website. Heroku will not store any passing data.

## Other third parties

In case of embedded content your browser is also subject to other services with different privacy policies. The blog is configured to request the most basic and privacy preserving version of the embedded content that it supports. [To discover more check the CMS page about it.](https://gohugo.io/about/hugo-and-gdpr/).

The site is configured to use the strictest referrer policy possible when linking to external websites when possible.

All the social sharing buttons work without the libraries provided by them, they just link to internal URLs of the various platforms.

For services of Web tipping (Flattr, Brave Rewards) that rely on the browser (or an extension) recognizing a meta tag in the code of the blog and then reporting the usage statistics to their infrastructure, it's specified in their privacy policy that they store locally information about your interaction with the website and then send this information in anonymized form. You can learn more in their respective websites: [Flattr](https://flattr.com/privacy#:\~:text=Your%20browsing%20behavior%20in%20the%20Extension), [Brave Rewards](https://brave.com/publishers-creators-privacy/).

This blog also uses local storage and service workers to provide offline functionality.  All the work is done locally and it won't download content that has not been asked to.  This content will not be used to track or fingerprint users.
