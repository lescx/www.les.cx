+++
draft = false
#aliases = ['']

# Not a generic name like "Vorlesung: 2023-09-10" but a descriptive title!
title = 'Der Körper der komplexen Zahlen'
tldr = 'Die erste Vorlesung des Moduls Einführung in die Mathematik (für Informatiker:innen), Teilbereich Lineare Algebra behandelt die komplexen Zahlen. Am Ende der Vorlesung wird ein Ausblick gegeben auf den Fundamentalsatz der Algebra.'

# SEO ~150 chars max
description = ''
# SEO keywords
keywords = []

semesters = 1
modules = 'Einführung in die Mathematik: Lineare Algebra'
topic = 'Körper der komplexen Zahlen'
moduleNumber = 'INF-110-LA'

date = 2023-10-09T09:35:24+02:00
publishDate = 2023-10-09T09:35:24+02:00

includeToC = false
includeKaTeX = true
+++

* schnelles multiplizieren von Zahlen am Computer verlangt Hilfsmittel aus dem komplexen Zahlenbereich
* leichtes multiplizieren und dividieren von komplexen Zahlen kann mitteln Polarkoordinaten geschehen
* es gibt keine positiven oder negativen komplexen Zahlen ohne $\real$
* -1 = i

---

Video-Empfehlungen:

* [DorFuchs: Komplexe Zahlen (Mathe-Song)](https://www.youtube.com/watch?v=HRzQAnUl1C4)
* [Veritasium: How Imaginary Numbers Were Invented](https://www.youtube.com/watch?v=cUzklzVXJwo)

## Zahlenbereiche

Als Herleitung bis hin zu den komplexen Zahlen…:

* mit **ganzen Zahlen** kann man uneingeschränkt subtrahieren
* mit **rationalen Zahlen** kann man mit Sonderrolle der 0 ausgeschlossen uneingeschränkt dividieren
* mit **reellen Zahlen** schließt man zahlen wie pi, e,… mit ein
* mit **komplexen Zahlen** definieren wir $i = -1$
  * $x^{2} = -1$ -> keine Lösung in $\real$
  * Auch: $x^{2} = -r$ für $r > 0$ keine Lösung in $\real$

## Rechnen in $\Complex$:

### Vergleichen von komplexen Zahlen:

> Zwei komplexe Zahlen sind gleich wenn sowohl der Realteil, als auch der Imaginärteil gleich sind.

### Addition und Multiplikation

Für $z_{1}, z_{2} \in \Complex$ mit

$$
z_{1} = a + bi
z_{2} = c + di
$$

definieren wir

$$
z_{1} + z_{2} = (a+c)+(b+d)i
$$
$$
z_{1} + z_{2} = (ac-bd)+(ad+bc)i
$$

### Division

Bei der Division von **komplexen Zahlen** wird der Nenner des Bruchs zuerst komplex konjugiert, d.h. im Imaginärteil wird das Vorzeichen gedreht.

Jetzt kann der Bruch damit erweitert werden, womit letztendlich eine reelle Zahl im Nenner steht.

Beispiel:

$$
\frac{a+bi}{c+di}
$$

komplexe Zahl $z = c + di$

komplex konjugierte Zahl $\bar{z} = di$

$$
\frac{a+bi}{c+di} = \frac{(a+bi)(c-di)}{(c+di)(c-di)}
$$

Oben kann ausmultipliziert werden, unten die 3. binomische Formel angewendet werden.

$$
= \frac{ac+bd+(bc-ad)i}{c^{2}+d^{2}}
$$

$$
= \frac{ac+bd}{c^{2}+d^{2}}+\frac{bc-ad}{c^{2}+d^{2}}
$$

### Realteil und Imaginärteil

$$
Re(z) = \frac{ac+cd}{c^{2}+d^{2}}
$$

$$
Im(z) = \frac{bc-ad}{c^{2}+d^{2}}
$$

## Körper der komplexen Zahlen

* Was ist ein Körper?

Ein Körper ist eine algebraische Struktur (bspw. $\Complex$). Näheres im 3. Semester.

## Gaussche Zahlenebene

Mit den beiden Angaben Radius $r$ und Winkel "phi" $\varphi$ kann man ebenfalls genau angeben, wo sich eine komplexe Zahl befindet. Das nennt man die **Polarkoordinaten**.

$r$ ist dabei der Betrag von $z = |z|$.

$$
Gegenkathete = r \cdot cos(\varphi)
$$

$$
Ankathete = r \cdot sin(\varphi)
$$

## Polarform

$$
re^{i\varphi}
$$

## Eulersche Identität

$$
e^{i\pi} = -1
$$

## Eulersche Formel

$$
e^{i\varphi} = cos(\varphi) + s \cdot sin(\varphi)
$$

---

## Dokumente

* [Folien 00](/university/lineare-algebra-vorlesung-00.pdf)
* [Folien 01](/university/lineare-algebra-vorlesung-01.pdf)
