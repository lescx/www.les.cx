+++
draft = true
#aliases = ['']

title = 'A Summary of App Repositories for GrapheneOS'
subtitle = "Don't bully the app store with 12 apps! :("
# tl;dr
tldr = "If you use the sandboxed Google Play Services, the Google Play Store is currently the most trustworthy source to download apps from. Don't use the Aurora Store. Also, use Obtainium from GitHub to download your FOSS apps. Keep an eye on Accrescent."

# SEO ~150 chars max
description = 'A comparison and recommendation about different kind of sources to retrieve apps from for GrapheneOS.'
# SEO keywords
keywords = ['GrapheneOS', 'Aurora Store', 'F-Droid', 'Accrescent', 'Obtainium']

date = 2023-09-17T18:13:10+02:00
publishDate = 2023-09-17T18:13:10+02:00

includeToc = true
+++

Da häufig die Diskussion auftritt, worüber man Apps beziehen sollte über GrapheneOS, hier ein kurzes "How to" und "Why to" über die Thematik *App-Repos*.

Dieser Guide ziehlt auf die *sicherste* Methodik ab. Sicher heißt vertrauenswürdiges beziehen der quelloffenen App mit einer möglichst geringen Chance, dass die App manipuliert auf meinem Gerät landet.
Nette Nebeneffekte, die mit in die Auswahl einkalkuliert werden sollten:

- best practices
- moderne Codebase
- schnelle Updates im Store

Worauf dieser Artikel nur wenig Augenmerk drauf legt ist auf die Gefahr, dass 


## [Accrescent](https://accrescent.app/)

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

> linsui
> F-Droid Contributor
> Dec '21
>
> F-Droid can’t ensure the apps are safe. You still need to trust the upstream developers. We only do some basic check. \[…]
> Source: https://forum.f-droid.org/t/is-it-as-safe-as-it-is-from-fdroid-official-repo/15956/2

*What are basic checks, you may ask?*

> linsui
> F-Droid Contributor
> Jan '22
>
> When an app is submitted the first time, our issuebot scans the apk and reports permissions, trackers and non-free libs. We also check the apk with VirusTotals. Then we test it on a device to ensure it works well and there is no suspectious network connections. Our reviewers publishes thoes review in the comments of the MR. We don’t check it again for app updates. The fdroidserver scanner scan the repo for non-free libs only.
> Source https://forum.f-droid.org/t/is-it-as-safe-as-it-is-from-fdroid-official-repo/15956/12

Here are a few problems with F-Droid:
QUELLEN FÜR ALLES ANGEBEN!!!

- Outdated APK Client mit geringer minimum sdk
- Obsolete installation method HEIßt???
 - arbeiten aber an unattended updates
- Does not take advantage of modern appstore features??? Heißt
 - arbeiten aber an unattended updates
- moderation?
- No old app deletion --> SDK minimum like Google Play Store?
- FOSS Rules?
- Building and signing infrastructure, aber wird dran gearbeitet
- Update Approval times

Aber: https://f-droid.org/en/2023/09/03/reproducible-builds-signing-keys-and-binary-repos.html

https://privsec.dev/posts/android/f-droid-security-issues
https://twitter.com/GrapheneOS/status/1497272529223917575

Vorteile

F-Droid besitzt die Möglichkeit für reproducible builds. Aber fast keine App implementiert das :-)
Und das tatsächliche bauen ist zu kompliziert. Natürlich kein Problem von F-Droid, aber wie oft habt ihr eure Anwendungen, die ihr von F-Droid heruntergeladen habt, danach selbst gebaut?


## Aurora Store


## Sandboxed Google Play Store


## Obtainium
