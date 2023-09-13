+++
draft = false
aliases = ['']

title = 'Vorbereitung Mathe Mengenlehre'
subtitle = ''
topic = 'Mengenlehre'
description = ''
summary = ''

semesters = 1
modules = 'Vorbereitungskurs Mathematik 2023 Online'
moduleNumber = ''

keywords = []

date = 2023-09-10T08:13:11+02:00
publishDate = 2023-09-10T08:13:11+02:00

includeToC = true
includeKaTeX = true
+++

Der Begründer der Mengenlehre ist Georg Cantor. Die aktuelle Definition, was eine Menge ist, kommt allerdings nicht von ihm. Ohne dazu eine konkrete Erklärung bieten zu können: seine Definition erlaubte einige Widersprüche. Die korrekte, widerspruchsfreie Definition von Mengen, Elementen und co. kommt später im Studium.

## Mengengleichheit

**Definition**

Zwei Mengen heißen **gleich**, wenn sie dieselben Elemente enthalten. Formal geschrieben:

$$
A = B \iff \forall x: (x \in A \iff x \in B)
$$

- Die Reihenfolge der Elemente in einer Menge spielt keine Rolle.
- In einer Menge kann ein Element mehrfach aufgeführt werden. Diese Menge "besitzt" dieses Element dennoch nur einmal.

**Beispiel**

$M_1 = \set{a}$ und $M_2 = \set{a,a}$. Also folgt $M_1 = M_2$

## Beschreibung von Mengen

Mengen können durch Eigenschaften oder durch einfache Aufzählung beschrieben werden.

$$
M = \set{x|P(x)}
$$

- **Sprechweise:** *$M$ ist die Menge aller $x$, für die die Aussage $P(x)$ wahr ist.*

**Beispiel**

$$
\set{x | x \in \N \land x \pmod 2 = 0}
$$

### Leere Menge

Gemäß der Mengengleichheit gibt es genau eine Leere Menge $\emptyset$.

### Übungen

$$
M_1 = \set{3,4,5,6,7}
$$

$$
M_1 = \set{x | x > 2 \land x < 8}
$$

$$
M_2 = \set{x | \frac x 3 \in \N}
$$

$$
M_2 = \set{3,6,9,12,…}
$$

bzw.

$$
M_2 = \set{0,3,6,9,12,…}
$$

## Teilmengen

**Definition**

Eine Menge $A$ heißt **Teilmenge** einer Menge B, geschrieben $A \subseteq B$, wenn jedes Element von $A$ auch Element von $B$ ist.

Formal geschrieben:

$$
A \subseteq B \iff \forall x: x \in A \implies x \in B
$$

### Wichtige Anmerkungen

- Wenn es ein Element in $B$ gibt, das nicht in $A$ enthalten ist, spricht man von einer **echten Teilmenge**, geschrieben $A \subset B$.
- Manchmal wird auch von einer *unechten Teilmenge* gesprochen wenn gilt $M_1 = M_2$
- Wenn es ein Element in $A$ gibt, das nicht in $B$ enthalten ist, ist $A$ *keine* Teilmenge von $B$.
- Die leere Menge $\emptyset$ ist die Teilmenge jeder Menge.

### Rechenregeln / Eigenschaften

- Reflexivität: $A \subseteq B$
- Symmetrie
- Antisymmetrie: $A \subseteq B \land B \subseteq A \implies A = B$
- Transitivität

### Darstellung von Mengen

*Notiz an mich selbst: Wie kann man Venn-Diagramme hier einbetten? Mudd du mal gucken, 'min Jung!*

## Potenzmengen

**Definition**

Für eine Menge $A$ heißt die Menge $\mathcal{P}(A)$ aller Teilmengen von $A$ die **Potenzmenge** von $A$.

Formal:

$$
\mathcal{P}(A) = \set{M | M \subseteq A}
$$

---

**Definition**

Für eine *endliche* Menge $A$ ist die **Mächtigkeit** (Kardinalität) $\mid A \mid$ die Anzahl der in $A$ erhaltenen Elemente.

**Hinweis**

Wenn $A$ eine Menge mit endlich vielen Elementen ist, dann hat $\mathcal{P}(A)$ genau $2^{\mid A \mid}$ Elemente. Dies ist auch ein Grund, warum die Potenzmenge von $A$ manchmal als $2^{A}$ bezeichnet wird. Es gilt also:

$$
\mid \mathcal{P}(A)\mid = \mid 2^{A}\mid = 2^{\mid A \mid}
$$

**Beispiel**

Für eine Menge mit drei Elementen (Mächtigkeit = 3) muss die Potenzmenge genau $2^{3} = 8$ Elemente enthalten.

Die Potenzmenge der leeren Menge hat genau ein Element, nämlich die leere Menge selbst, denn $2^{0} = 1$.

## Durchschnitt und Vereinigung

[Verweis auf Wikipedia](https://de.wikipedia.org/wiki/Mengenlehre#Schnittmenge)

- **Durchschnitt $\cap$**, auch genannt Schnittmenge
  - Der Durchschnitt zweier Mengen und ist die Menge, die aus allen Elementen besteht, die sowohl zu $A$ als auch zu $B$ gehören.
- **Vereinigung $\cup$**, auch genannt Vereinigungsmenge

---

**Definition *disjunkt*, *durchschnittsfremd***

Zwei Mengen heißen **disjunkt**, wenn ihr Durchschnitt die leere Menge $\emptyset$ ist.

## Differenz und Komplement

---

## Read further…

- Empfehlenswerte Zusammenfassung: [Mengen und ihre Eigenschaften](https://www.grund-wissen.de/mathematik/mengenlehre/mengen.html). Das ganze Projekt [grund-wissen.de/mathe](https://www.grund-wissen.de/mathematik/index.html) ist im übrigen auch auf [GitHub](https://github.com/grund-wissen/grundwissen-mathematik) einsehbar.
- [Wikipedia](https://de.wikipedia.org/wiki/Mengenlehre)
- [OPAL](https://bildungsportal.sachsen.de/opal/auth/RepositoryEntry/11530829826/CourseNode/94241506426765)
