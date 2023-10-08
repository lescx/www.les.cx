+++
draft = false
#aliases = ['']

title = 'Living in the TTY'
subtitle = '> Do you expect to run the X Window System? no'
tldr = ''

# SEO ~150 chars max
description = ''
# SEO keywords
keywords = []

date = 2023-10-08T10:32:00+02:00
publishDate = 2023-10-08T10:32:00+02:00

includeToc = false
+++

*Oct 2023: This article is in WIP since 2022. Once I successfully finished my project, this disclaimer will disappear. Also, then the article will be written in English. Return later.*

Seit 2021 denke ich viel darüber nach, mein digitales Leben vollständig in ein "OG Terminal" zu verschieben. Viel Charme hatte ich insbesondere dem Gedanke abgewonnen, meine Arbeiten an einem alten Macintosh mit OpenBSD zu erledigen. Alter Monitor, alte Tastatur, hohe Stromkosten.

Der Plan ist, ohne grafische Oberfläche zu arbeiten. Das Ganze ist auch aus einem Verdruss entstanden, dass alle Betriebsysteme *schlecht* sind. Plan9 hätte ein gutes Betriebsystem werden können mit grafischer Oberfläche by design, aber Plan9, sein nicht-Erfolg und mehr, ist ein eine ganze Artikelserie für sich.

Im Grunde genommen wollte ich unnoetiges herumsurfe im Internet minimieren, mich tiefer mit OpenBSD auseinandersetzen und C und Rust lernen. Ich höre schon die Stimmen, die sagen *aber ist das nicht total unnötig und macht das Dein Leben nicht viel schwerer als es sein müsste?* Ja.

Ich möchte wissen, ob es möglich ist, in 2022 zurück in das digitale Mittelalter zurückzufallen - auch, wenn ich mich täglich frage, wie weit wir wirklich fortgeschritten sind seit dem Ende des virtuellen Terminals als Benutzeroberfläche.

Im November 2021 kaufte ich mir ein macbook pro 2014 14" mit einem M1 Pro. 32 GB Ram, 1 TB SSD Geschwindigkeitsklasse "alter finne, iss dat schnell". Voellig uebertrieben.
Davor benutzte ich erst ein Thinkpad T440p, danach ein X1 Carbon Gen 4. Beide male lief Fedora Workstation, später Silverblue, als Betriebssystem. Den T440p verkaufte ich irgendwann, der X1 ist immernoch in Gebrauch, allerdings von meiner Freundin. ~~Linux Mint.~~ Update: Fedora Silverblue. :-)

Ich glaube, ich hatte es nicht genug betont. Völlig übertrieben. Teurer Luxus, der mir gut gefallen hat - 2700 Euro hat mich der Spass gekostet, den ich mir als Student eigentlich nicht leisten konnte. Aber Ratenzahlung regelt, 'ne? Ich arbeite parallel und komme gut ueber die Runden von Monat zu Monat, aber eine Ratenzahlung verteilt die 2700 Euro auch nur ueber einen laengeren Zeitrahmen und macht den Laptop nicht guenstiger.

In meiner Gymnasialzeit hatte ich ein bereits Interesse an OpenBSD. OpenBSD ist nicht so sicher, wie es sich gerne aufspielt. Aber OpenBSD ist "sane". Es ist nicht verkopft mit immer größer werdender Komplexität. Linux ist nur ein Ballon, der zu platzen scheint. Und für mich ist er schon seit vielen Jahren geplatzt.OpenBSD's Art der Kommunikation per Mailinglisten, die sehr gute Dokumentation, die zum "machs doch selber und geh' mir nicht auf den Keks mit Deinen Fragen"-Mentalität sagt mir zu.

Ehrlich gesagt hatte ich Mitte 2022 schon einmal versucht, auf mein macBook Pro OpenBSD via Asahi Linux zu installieren (EFI Partition, ueber die dann OpenBSD auf einer separation Partition laufen soll). Aber ich bin kläglich gescheitert und ich hatte zum ersten Mal in meinem Leben ein Gerät gesoftbricket. Obwohl ich seit 2013 (mit 11 damals!) handys gerootet habe. Mit Hilfe eines Mac's von einer Freundin konnte ich meinen Laptop wieder zum Leben erwecken - aber das war auch ein Akt von mehreren Stunden und keine Nachmittagsbeschaeftigung, die ich jemanden in einer Bibliothek empfehlen würde (beep beeeep). Aber gut, ich schweife ab.

## Was mache ich an meinem Rechner?

### ist mir wichtig/ist notwendig

- Private Emails lesen und beantworten (IMAP/SMTP via mailbox.org)
	- Mailinglisten!
- Outlook Emails via Microsoft Exchange (University Emails, koennte ich im Notfall auch per Handy erledigen)
- RSS
- IRC
- Kalender + Erinnerungen
- Notizen
- Markdown Notizen schreiben + digitaler Zettelkasten
- Musik hören? Streaming? Lokal?
- Passwörter verwalten
- Nachrichten verschlüsseln via PGP/age
- SSH
- Torrents
- YubiKeys nutzbar
- programmieren
- Bücher lesen
- PDF's?

### mache ich im Moment, aber ist häufig sinnlos

- Twitch streams schauen
- Videos schauen
- das Internet nutzen?!

---

Does work:

* Ethernet/Wireless internet
* Music [amused](https://projects.omarpolo.com/amused.html)
* IRC (TLS only) [catgirl](https://git.causal.agency/catgirl/about/)
* RSS/Atom: [sfeed](https://codemadness.org/sfeed-simple-feed-parser.html)
* HTTPS browser
* gopher/gemini
* Mail neomutt? [meli](https://github.com/meli/meli)? himalaya?
* Helix+hugo
* Development (in my case C, Shell, Lisp (Scheme), Python, Rust, HTML+CSS)

Doesn't work

* Watch/Edit videos
* "Modern" web browser
* Images
* Properly formatted PDFs
* Blender 'n stuff

## Installation

Beginn:

* Installation ohne Spiele, Xorg-basierten Pakete,… --> Achtung! Bei Upgrade ist Mehrarbeit angesagt!
* Kein Xorg (Xenocara) darf installiert werden
* Nur ein TTY mit tmux ist erlaubt

> Do you expect to run the X Window System? [yes]
>no

