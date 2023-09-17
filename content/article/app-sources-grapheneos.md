+++
draft = true
#aliases = ['']

title = 'A Summary of App Repositories for GrapheneOS'
subtitle = "Don't bully the app store with only 12 apps… :("
# tl;dr
tldr = 'Ideally, only use the GrapheneOS "Apps" app and Accrescent - maybe that is a possibility in the future. If you use the sandboxed Google Play Services, download your apps from the Google Play Store. Download Obtainium from GitHub for apps not found in the Google Play Store. Do not use Aurora Store or F-Droid anymore. Do not download non-app stores from websites.'

# SEO ~150 chars max
description = 'A comparison and recommendation about different kind of sources to retrieve apps from for GrapheneOS.'
# SEO keywords
keywords = ['GrapheneOS', 'Aurora Store', 'F-Droid', 'Accrescent', 'Obtainium']

date = 2023-09-17T18:13:10+02:00
publishDate = 2023-09-17T18:13:10+02:00

includeToc = true
+++

Da in den GrapheneOS Matrix-räumen täglich die Frage aufkommt, worüber denn Apps bezogen werden sollen, hier ein kurzes "How to" und "Why to" über die Wahl von App repositories.

Dieser Guide zielt auf die *sicherste* Methodik ab. Sicher heißt vertrauenswürdiges beziehen der App mit einer möglichst geringen Chance, dass die App manipuliert auf meinem Gerät landet.

Worauf dieser Guide keinen Augenmerk legt, 
Ob die App selbst vertrauenswürdig ist und mit einem ausreichendem Eigenmerk auf best practices legt, muss jeder selbst überprüfen. 

Nebeneffekte, die mit in die Auswahl einkalkuliert werden sollten:

- best practices
- moderne Codebase
- schnelle Updates im Store

Ganz kurzer disclaimer: es macht keinen Unterschied, ob eine App auf GitHub, F-Droid oder im Google Play Store seit zwei Jahren nicht mehr geupdated wurde. In dem Fall heißt die Antwort auf die Ausgangsfrage: installiere die App gar nicht!

## Accrescent

[Accrescent](https://accrescent.app/)

Was wir wollen: Entwickler signieren ihre Anwendung. Accrescent signiert nicht, aber lässt nicht installieren, wenn signatur nicht passt.
Hoffnung für die Zukunft.

## APKs from Official Websites

Ich glaube, das machen vor allem Windows-Nutzer gerne, da es auf der Plattform lange Zeit selbstverständlich war, auf die offizielle Website eines Programms zu gehen und die .exe oder .msi Datei herunterzuladen. Das sollte man weder auf Windows tun, noch auf anderen Plattformen. Es soll mir aber nicht um Windows gehen - das würde ein eigener Beitrag werden.

Wenn es die offizielle Seite eines Programms ist, dann ist das herunterladen einer App über die Website genauso gefährlich oder ungefährlich wie über Repositories wie GitHub - je nachdem, wie die Website konfiguriert ist, würde ich vermutlich eher über GitHub herunterladen.
Ebenso: man sollte den Hash + PGP signatur überprüfen. All das kommt auf einer Website (und GitHub) i.d.R. nicht vor (aber geht via OpenKeyChain!).

Ablauf, bis die Datei auf der Website landet:

Der Prozess, bis das Programm letztlich auf der Website landet, ist leider sehr undurchdringlich. Jedes Projekt (jeder Entwickler) wird das anders händeln. Letztlich wird es aber ungefähr so aussehen:

1. Bauen der Anwendung (oder *der Anwendungen* bei mehreren Plattformen)
2. (Optional) Hash generieren, Anwendung mit externer Signatur signieren, Hash signieren --> das ganze setzt i.d.R. einen ordentlich geschützten [PGP]-Schlüssel vorraus. Leider wissen die wenigsten Entwickler, wie man PGP "richtig nutzt". QubesOS macht es richtig. Nutzerfreundlich und "einfach" für Normalos ist der Weg aber nicht.
3. Alle Dateien auf einen Webserver hochladen und damit anderen bereitstellen
4. Profit?

Grundsätzlich ist an dem Prozess nichts verkehrt - ein Programm bauen auf dem Entwicklerrechner und hochladen. Code updaten, neu bauen, neu hochladen.

Das Problem liegt darin, dass man wenig einsicht darüber hat, was auf dem Weg seit oder während dem kompilieren des Programmes alles passiert ist. Es ist kein besonders vertrauenserweckender Weg, ein Programm zu beziehen.
Und kein nutzerfreundlicher. Wie oft habt ihr die PGP-Signatur auf eurem Gerät für ein Programm überprüft? Am Computer mache ich das wenn nötig. Am Handy? Nope.

- Der Entwickler baut das Programm irgendwie, irgendwo und stellt eine APK-Datei auf einer Seite bereit. Das heißt aber nicht, dass der Nutzer diese auch zu Gesicht bekommt.
- Keine Security-scans möglich
- Kein Erzwingen von bestimmten features möglich

Vorteil:
- Wenn manipuliert, dann nur diese App und nicht automatisch alle Apps

## APK von GitHub Releases

- GitHub Releases sind nicht gleich GitHub releases. Letztlich sind GitHub releases nur git tags und nichts hält einen Entwickler (und oder bösartige Akteure) manipulierte APKs einzuschleußen.

 Vorteile:

- CI/CD möglich zum bauen von Quelle
- Wenn manipuliert, dann nur diese App und nicht automatisch alle Apps

## F-Droid (and derivates)

* GrapheneOS on Google Play Store and F-Droid https://nitter.net/GrapheneOS/status/1497273173364166662#m

> linsui
> F-Droid Contributor
> Dec '21
>
> F-Droid can’t ensure the apps are safe. You still need to trust the upstream developers. We only do some basic check. \[…]
> Source: https://forum.f-droid.org/t/is-it-as-safe-as-it-is-from-fdroid-official-repo/15956/2

*What are basic checks?*

> linsui
> F-Droid Contributor
> Jan '22
>
> When an app is submitted the first time, our issuebot scans the apk and reports permissions, trackers and non-free libs. We also check the apk with VirusTotals. Then we test it on a device to ensure it works well and there is no suspectious network connections. Our reviewers publishes thoes review in the comments of the MR. We don’t check it again for app updates. The fdroidserver scanner scan the repo for non-free libs only.
> Source https://forum.f-droid.org/t/is-it-as-safe-as-it-is-from-fdroid-official-repo/15956/12

* Outdated APK Client?
* Does not take advantage of modern appstore features?
    * Currently working on unattended updates
* moderation of apps?
* No old app deletion --> What is the SDK minimum - the Google Play Store does have a strict minimum?
* FOSS Rules?
* Building and signing infrastructure?
* Update Approval times?
* supports reproducible builds
    * around 200 Apps currently https://gitlab.com/obfusk/fdroid-misc-scripts/-/blob/master/reproducible/overview.md
    * who checks that before using it?

* [2023-09-03 Reproducible builds, signing keys, and binary repos](https://f-droid.org/en/2023/09/03/reproducible-builds-signing-keys-and-binary-repos.html)
* [2023-09-06 F-Droid Security Issues](https://privsec.dev/posts/android/f-droid-security-issues)

## Aurora Store

**Disclaimer:** Ich sollte an dieser Stelle noch einmal darauf aufmerksam machen, dass dieser Guide *nicht* die datensparsamste Methode sucht, seine Apps zu beziehen, sondern die sicherste, wie oben definiert.

Reasons, why you might want to use Aurora Store in the past:

* Man möchte "anonym" seine Apps wie WhatsApp und Netflix vom Google Play Store verwenden, ohne sich mit einem Google Konto anzumelden.
* Man möchte oder kann keinen Google Play Store nutzen
* der Google Play Store hat Sonderrechte auf dem eigenen Gerät und unterliegt nicht der App Sandbox von Android.

## Sandboxed Google Play Store

My disclaimer on [Aurora Store](#aurora-store) does apply as well.

* https://nitter.net/GrapheneOS/status/1497272529223917575

## Obtainium
