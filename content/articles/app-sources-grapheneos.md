+++
draft = false
aliases = ['/article/app-sources-grapheneos']

title = 'A Summary of App Repositories for GrapheneOS'
subtitle = "Don't bully the app store with only 12 apps… :("
# tl;dr
tldr = 'Ideally, only use the GrapheneOS "Apps" app and Accrescent - maybe that will be a possibility in the future. If you use the sandboxed Google Play Services, download your apps from the Google Play Store. Download Obtainium from GitHub for apps not found in the Google Play Store. Do not use Aurora Store or F-Droid anymore. Downloading apps from official websites should be your last resort.'

# SEO ~150 chars max
description = 'A comparison of different sources to retrieve apps from for GrapheneOS.'
# SEO keywords
keywords = ['GrapheneOS', 'Aurora Store', 'F-Droid', 'Accrescent', 'Obtainium']

date = 2023-09-17T18:13:10+02:00
publishDate = 2023-09-17T18:13:10+02:00

includeToc = true
+++

**Disclaimer:** This post is still in a very early WIP state! This post is public because I want to collaborate with the GrapheneOS community on it!

Since in the GrapheneOS matrix rooms the question arises almost daily about the best way to obtain apps, this is a short "how to" and "why to" for GrapheneOS users. The aim is to obtain apps from a source that is as trustworthy and secure as possible.

I try to keep the explanation for each section as short as possible.

## APKs from Official Websites

I guess Windows users in particular like to do this because for a long time it was a matter of course on the platform to go to the official website (or not) of a specific program and download the .exe or .msi file. For the most part, you shouldn't do that on Windows, nor on other platforms.

There is no signature check happening if the APK is *actually* coming from the developer(s).
Also: Do you check the APK hash and PGP signature on android? Probably not.

Not a particularly confidence-inspiring way to obtain an app.
And not a user-friendly one. How often have you checked the PGP signature on your phone for a programme?


## APK von GitHub Releases

* GitHub releases are not all the same. Ultimately, GitHub releases are just git tags and nothing stops a developer (and or malicious actors) from injecting manipulated APKs. 
* Uniform and simpler infrastructure for the developer and user in comparison to websites.
* Signatures can be verified but UI doesn't tell at all if signing key has changed.
    * Means, similar process to GPG via website
* CI/CD possible to build APKs using GitHub Pipeline.


## F-Droid (and derivates)

I recommend this article on [F-Droid Security Issues](https://privsec.dev/posts/android/f-droid-security-issues) which goes into great detail. ([Wayback Machine](http://web.archive.org/web/20230000000000*/https://privsec.dev/posts/android/f-droid-security-issues))

See also…

* [2023-09-03 F-Droid: Reproducible builds, signing keys, and binary repos](https://f-droid.org/en/2023/09/03/reproducible-builds-signing-keys-and-binary-repos.html)
* [2022-02-25 GrapheneOS: On Google Play Store and F-Droid](https://nitter.net/GrapheneOS/status/1497273173364166662)

tl;dr: Luckily, there is no need to install apps from F-Droid anymore.


## Sandboxed Google Play Store

I want to point out again that this guide is *not* looking for the most private way to obtain its apps, but the most secure, as defined above.

* https://nitter.net/GrapheneOS/status/1497272529223917575
* proper building and signing
* Developer and Google sign the app.


## Aurora Store

Reasons, why you might want to use Aurora Store in the past:

* One would like to use "anonymously" one's apps such as WhatsApp and Netflix from the Google Play Store without logging in with a Google account.
* One does not want to or cannot use a Google Play Store.
* Security issue: The Google Play Store has special rights on one's own device and is not subject to the same App Sandbox as other apps are.


## Obtainium

Most repository hosting provider (GitHub, GitLab, Codeberg,…) allow subscribing to a project via RSS feeds. Many even support multiple RSS feeds on a per commit or per release basis.

[Obtainium](https://github.com/ImranR98/Obtainium) builds on top of this concept and allows a direct download of apps straight from the source.
Obtainium also scrapes from some website app sources like MullvadVPN, Signal. See the documentation for a long list of supported sources.

The UI and codebase is modern, written in Dart. Updates can be rolled out fast by design. The project is pretty new so not everything works perfectly (e.g. GitLab requires an API key to download apps) - but it works as a daily driver!

Still, the core problem remains: (GitHub) releases aren't a perfect solution. But it is currently the best solution for FOSS apps out there.


## Accrescent

And here we are… The app source with 12 apps. [Accrescent](https://accrescent.app/).

* Modern codebase with focus on privacy and security!
* Accrescent does not sign but developer
    * They actually care if the signature changes!!! (Looking at you, F-Droid!)
