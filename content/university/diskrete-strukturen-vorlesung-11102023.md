+++
draft = false
#aliases = ['']

# Not a generic name like "Vorlesung: 2023-09-10" but a descriptive title!
title = 'Mengenlehre Teil 1'
topic = 'Mengenlehre'
tldr = 'Der Spaß der diskreten Strukturen beginnt mit der Einführung in die Mengenlehre.'

# SEO ~150 chars max
description = ''
# SEO keywords
keywords = []

semesters = 1
modules = 'Einführung in die Mathematik: Diskrete Strukturen'
moduleNumber = 'INF-110-DS'

date = 2023-10-11T10:59:31+02:00
publishDate = 2023-10-11T10:59:31+02:00

includeToC = true
includeKaTeX = true
+++

## Wichtige Seiten

* [Übersicht Modul](https://tu-dresden.de/mn/math/algebra/das-institut/beschaeftigte/antje-noack/dateien/diskrete-strukturen-2019-20)
* [Skript](https://wwwpub.zih.tu-dresden.de/~bodirsky/Diskrete-Strukturen.pdf)
* [Prof. Bodirsky (YouTube)](https://www.youtube.com/@bodirsky)

---

Inhalt:

* Grundlagen der Mathematik und theoretische Informatik
* Graphen, Wörter, Ordnungen…
  * "Rohstoffe der Datenverarbeitung"

Es gibt in diesem Modul keine Vorlesungsschriften, da der Prof./die Prof. an der Tafel schreibt. Allerdings gibt es ein Skript (wenn die Website funktioniert).

## Mengenlehre

> Mengenlehre ist die Grundlage der modernen Mathematik

* $e \in M$ bedeutet $e$ ist Element der Menge $M$.
* $e \notin M$ bedeutet $e$ ist nicht Element der Menge $M$.
* $\emptyset$ steht für die Menge ohne Elemente "leere Menge".
* $\LaTeX$: $A \subset B$ heißt **wahre Teilmenge** (`\subset`)
* $\LaTeX$: $A \subseteq B$ heißt Teilmenge oder gleich (`\subseteq`)

**Beispiel:**

* $\set{1,2,3}$ steht für die Menge, die genau die Elemente 1,2,3 enthält.
* $\set{\{1,2\},3}$ steht für die Menge mit genau den Element $\set{1,2}$ und $3$. $1$ ist kein Element der Menge.

### Mächtigkeit

$|M|$ steht für die Anzahl der Element von M (Mächtigkeit).

* $\vert\set{1,2,3}\vert = 3$
* $\vert\set{\set{1,2},3}\vert = 2$

#### Unendliche Mächtigkeit

Beispielsweise die Menge mit unendlich vielen Elementen wie bspw $\N$ (beginnend bei dem Herrn Prof. bei 0) oder $\Z$.

$|\N|$ = unendl.

**Randnotiz:** *Prof. begründet die 0 für die natürlichen zahlen u.a. auch damit. eine Menge hat immer die Mächtigkeit von einer natürlichen Zahl odre unendlich. Eine leere Menge hat die Mächtigkeit von 0, d.h. 0 ist eine natürliche Zahl.*

### Mengenangaben durch Aussonderung

Schreiben $\set{x \vert Bedinung(x)}$ für die Menge aller $x$, die $Bedingung(x)$ erfüllen.

### Rechenregeln

Schnitt und Vereinigung sind idenpotent.

* $A \cap A = A$
* $A \cup A = A$

Schnitt und Vereinigung sind kommutativ.

* $A \cup B = B \cup A$
* $A \cap B = B \cap A$

Schnitt und Vereinigung sind assoziativ.

* $(A \cap B) \cap C = A \cap (B \cap C)$

Dementsprechend kann man manchmal Klammern auch weglassen.

### Unendliche Schnitte und Vereinigungen

M ist eine Menge. Für jedes $i \in M$ sei $S_{i}$ eine Menge.

**Definition Schnitt:**

$\bigcap_{i \in M} := \set{\forall x \in M \vert x \in S_{i}}$

**Definition Vereinigung:**

$\bigcup_{i \in M} := \set{\exists x \in M \vert x \in S_{i}}$

**Beispiel:**

Für $i \in \N$ sei $S_{i}$ := {0,1,2,3,4,…,i-1} 

* $S_{0} = \set{\emptyset}$
* $S_{1} = \set{0}$
* $S_{2} = \set{0,1}$

### Komplement

**Definition: Komplement**

Eine feste, große Menge $U$ (bspw. $\N$). $M$ ist eine Teilmenge von $U$.

Das Komplement ist anschließend folgend definiert:

$$
\overline{M} := U \setminus M = \set{x \in U \vert x \notin M}
$$

### Weitere Rechenregeln

Distributivität von Schnitt über Vereinigung und Vereinigung über Schnitt

$$
A \cap (B \cup C) = (A\cap B)\cup (A\cap C)
$$

$$
A \cup (B \cap C) = (A\cup B)\cap (A\cup C)
$$

### Paare und Produkte

* $(a,b)$ ist ein geordnetes Paar aus den Mengen $a,b$.
* $(a,b) \neq (b,a)$, falls $a \neq b$
* Die Reihenfolge spielt eine Rolle.
* geordnetes Paar != "Paarmenge" ({a,b}={b,a})

Gesucht ist eine Menge (a,b) mit der Eigenschaft, dass (a,b) = (c,d), dann a=c und b=d.

**Definition:** geordnetes Paar

$$
(a,b) = \set{\set{a,b},{a}}
$$

**Frage:** *Würde auch $(a,b):=\set{\set{a,b},a}$ als Definition funktionieren?* – Nein - aber warum?

### Produktmenge

Das Produkt $A \times B$ von Mengen A und B ist definiert als

$$
A \times B := \set{(a,b) | a \in A \land b \in B}
$$

#### Notiz

$\vert A \times B \vert = \vert A \vert * \vert B \vert$

### Relationen

#### Definition Relationen

Eine Relation (zwischen A und B) ist eine Teilmenge von $A \times B$.

#### Beispiel

* $A = \set{0,1}$
* $B = \set{1,2}$

Eine Relation wäre: $\set{(0,1),(1,2)}$

#### Beispiel

Eine Relation $R \subseteq A \times A : \set{(a,b)\vert "Internetsetite-a-verweist-mit-link-auf-b"}$

Verweis hierbei auf den Begriff *gerichteter Graph*.

### Potenzmenge

#### Definition Potenzmenge

Wir haben eine Menge A. Die Potenzmenge von $A$ ist

$\mathcal{P}(A)$ := die Menge aller Teilmengen von $A = \set{B \vert B \subset A}$

$\set{1,2,3} \implies \mathcal{P}({1,2,3}) = \set{\set{1},\set{2},\set{3},\set{1,2},\set{1,3},\set{2,3},\set{1,2,3},\set{\emptyset}}$

#### Notiz

$\vert \mathcal{P} \vert = 8 = 2^3$
