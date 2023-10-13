+++
draft = false
#aliases = ['']

# Not a generic name like "Vorlesung: 2023-09-10" but a descriptive title!
title = 'Vorlesung Mengenlehre Teil 2'
topic = 'Mengenlehre'
tldr = ''

# SEO ~150 chars max
description = ''
# SEO keywords
keywords = []

semesters = 1
modules = 'Einführung in die Mathematik: Diskrete Strukturen'
moduleNumber = 'INF-110-DS'

date = 2023-10-13T10:57:01+02:00
publishDate = 2023-10-13T10:57:01+02:00

includeToC = false
includeKaTeX = true
+++

## Binomialkoeffizient

*Notiz an mich selbst: schaue nochmal eine "simple" Beschreibung für den Binomialkoeffizient an!*

### Definition

$$
\binom{n}{k}
$$

> Deutsch: n über k

> Englisch: n choose k

Bezeichnet die Anzahl aller k-elementiger Teilmengen einer n-elementigen Menge.

### Beispiel

* $\binom{n}{0} = \set{\emptyset} = \binom{n}{n} = 1$
* $\binom{5}{2} = \set{12,13,14,15,23,24,25,34,35,45} = 10$

---

### Herleitung der Formel

* Für $n \in \N$ schreiben wir $n!$ (*n factorial*) für $n*(n-1)*...*1$.
* $0! = 1$.
* $n!$ zählt die Anzahl der Möglichkeiten n Elemente anzuordnen.

**Proposition:**

> Für alle $n,k \in \N$ gilt

$$
\binom{n}{k} = \frac{n!}{k!*(n-k)!}
$$

**Beispiel:**

$$
\binom{5}{2} = \frac{5!}{5!*(5-2)!} = \frac{5-4}{2} = 10
$$

* $\binom{n}{2} = \frac{n*(n-1)}{2}$ ist ein Spezialfall.

### Beweis (der Proposition)

> Um eine k-elementige Teilmenge zu bilden, wähle erstes Element, dann zweites, usw. bis zum k-ten Element. Dafür gibt es $\frac{n!}{(n-k)!}$ viele Möglichkeiten. Jeweils $k!$ viele Möglichkeiten führen zur gleichen Teilmenge.

---

## Beobachtung

> Für alle $n,k \in \N$ gilt $\binom{n}{k} = \binom{n}{n-k}$.

### Algebraischer Beweis

$$
\binom{n}{k} = \frac{n!}{k!*(n-k)!} = \frac{n!}{(n-k)!(n-(n-k))!}  = \binom{n!}{n-k}
$$

n-(n-k)=n-n+k=k

### Kombinatorischer beweis: "Doppeltes Abzählen"

Beispiel Fußballteam

1. aus n Spieler:innen k auswählen, die spielen
2. aus n Spieler:innen n-k auswählen, die nicht spielen


## Beobachtung

Für alle $n,k \in \N$ gilt

$$
k * \binom{n}{k} = n * \binom{n-1}{k-1}
$$

Warum gilt das?

### Algebraischer Beweis

$$
k * \frac{n!}{(n-k)!*k!} = n * \frac{(n-1)!}{(k-1)!*((n-1)-(k-1))!}
$$

$$
= \frac{n!}{(k-1)!(n-k)!}
$$

*Habe ich das verstanden? Nein.*

### Kombinatorischer Beweis: Doppeltes abzählen

1. Aus $n$ Spieler:innen $k$ auswählen, die spielen $\binom{n}{k}$ und danach Kapitän:in bestimmen ($* k$)
2. Wähle zuerst Kapitän:in aus aus $n$ Möglichkeiten und danach das restliche Team $\binom{n-1}{k-1}$.

*Habe ich das verstanden? Ja. Gefällt mir besser.*

### Beobachtung

Für alle $n \in \N$ gilt:

$$
\sum{k=0}{n} \binom{n}{k} = \bimom{n}{0} + \binom{n}{1} + \binom{n}{2} + ... + \binom{n}{n} = 2^{n}
$$

### Kombinatorischer Beweis

Die oben genannte Formel zählt die Anzahl **aller** Teilmengen von {1,...,n}, also $\vert\mathcal{P}(\set{1,...,n})\vert = 2^{n}$

Für jedes Element wird entschieden, ob es aufgenommen wird (2 Möglichkeiten) und das n oft. Also $2^{n}$.

---

## Palcal'sches Dreieck

```
    1
   1 1
  1 2 1
 1 3 3 1
1 4 6 4 1
```

### Proposition

Für alle n, k in N gilt

$$
\binom{n+1}{k} = \binom{n}{k-1} + \binom{n}{k}
$$

### Kombinatorischer Beweis

Sei $M$ eine $n+1$ elementige Menge,  $x \in M$ beliebig aussuchen.

Bilde eine k-elementige Teilmenge von $M$, dafür genau eine der beiden Möglichkeiten.

1. $x$ wird ausgewählt. Dafür bleiben $\binom{n}{k-1}$ Möglichkeiten.
2. $x$ nicht ausgewählt. Dafür bleiben $\binom{n}{k}$ Möglichkeiten.

---

betrachten: $R := \set{x|x \notin x}$

Achtung, diese Schrift ist widersprüchlich!

Ist $R \in R$?

* Falls ja, dann erfüllt R die Bedingung, dass $R \notin R$
* Falls nein, dann erfüllt R die Bedingung, dass $R \in R$

**In beiden Fällen erhalten wir einen Widerspruch.**

Deshalb…

## Axiomssystem der Mengenlehre

Dieses löst die Widersprüche auf, wird allerdings noch nicht bis zum Ende behandelt.

https://en.wikipedia.org/wiki/Zermelo%E2%80%93Fraenkel_set_theory
ZERMELS FRAENKEL (ZF)????

1. Axiom: *Zwei Menge mit den gleichen Elementen sind gleich "Extensionalität"*
2. Axiom: *Es gibt die leere Menge $\emptyset$. Es gibt eine Menge, die keine Elemente hat.*
3. Axiom: *Für alle Mengen A,B gibt es die Paarmenge $\set{A,B}$, d.h. die eindeutige Menge mit exakt den Elementen A und B.* (Es darf natürlich auch A=B gelten)

Diese drei Axiome schließt bisher auf kein, ein oder zwei Elemente (aber alle Elemente sind die leere Menge)

4. Axiom: **Vereinigung** *Für jede Menge $M$ gibt es eine Menge, die gleich der Vereinigung der Mengen in $M$ ist.* $\bigcup{M}$ (Das soll heißen $\set{x|x \in A, A \in M}$

* $M = \set{\set{1,2},\set{2,3,4}}$
* $\bigcup{M} = \set{1,2,3,4}$

*Eine Hierarchieebene wird abgetragen.*

5. Axiom: 
