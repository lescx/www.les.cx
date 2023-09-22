+++
draft = false
title = 'Vorlesung: Logik, Mengen und Funktionen'
subtitle = ''
topic = 'Logik, Mengen und Funktionen'
description = 'Nach einer Begrüßung zum diesjährigen Brückenkurs werden in der 1. Vorlesung ein paar grundlegende Begriffe und Bezeichnungen eingeführt, die in der Mathematik immer mal wieder auftauchen. Das betrifft vor allem Grundlagen aus der Aussagenlogik und der Mengenlehre. Zudem wird der Begriff der Funktion als eindeutige Zuordnung eingeführt. In späteren Vorlesungen des Brückenkurses wird es dann noch genauer konkret um reelle Funktionen gehen, also Funktionen, bei denen sowohl die Ausgangsgrößen als auch die zugeordneten Größen reelle Zahlen sind.'
summary = ''

semesters = 1
modules = 'Brückenkurs Mathematik 2023'
moduleNumber = ''

keywords = []

date = 2023-09-21T08:29:45+02:00
publishDate = 2023-09-21T00:00:02+02:00

includeToC = true
includeKaTeX = true
+++

## Logik

### Aussagen und Wahrheitsgehalt

**Beispiel:** Elementaraussagen identifizieren

Zerlege die Aussage
*Ein Polynom f mit ungeradem Grad hat in R mindestens eine Nullstelle.*
in ihre Elementaraussagen (= Grundbausteine).

* **(A):** $f$ ist ein Polynom
* **(B):** $f$ hat ungeraden Grad.
* wenn **(A)** und **(B)** wahr ist, dann ist auch **(C)** wahr
* **(C):** $f$ hat mindestens eine Nullstelle

($f$ ist ein Polynom) $\land$ ($f$ hat ungeraden Grad) $\implies$ ($f$ hat eine Nullstelle)

**Beispiel:** Wahrheitstabelle

Weise mit Hilfe einer Wahrheitstabelle nach, dass $p \iff q$ äquivalent ist zu
$p \implies q \land \neg p \implies \neg q$.

| $p$ | $q$ | $p \iff q$ | $p \implies q$ | $\neg p \implies \neg q$ | $p \implies q \land \neg p \implies \neg q$ |
| --- | --- | ---------- | -------------- |:------------------------:|:-------------------------------------------:|
|  w  |  w  |      w     |       w        |               w          |                       w                     |
|  w  |  f  |      f     |       f        |               w          |                       f                     |
|  f  |  w  |      f     |       w        |               f          |                       f                     |
|  f  |  f  |      w     |       w        |               w          |                       w                     |


---

Was ist mit der Aussage
*Erbspüree oder Nudelgratin und Tomatensalat*
gemeint?

| E | N | T | $E \lor (N \land T)$| $(E \lor N) \land T)$ |
| - | - | - | ------------------- | --------------------- |
| w | w | w |          w          |           w           |
| w | w | f |          w          |           f           |
| w | f | w |          w          |           w           |
| f | w | w |          w          |           w           |
| w | f | f |          w          |           f           |
| f | w | f |          f          |           f           |
| f | f | w |          f          |           f           |
| f | f | f |          f          |           f           |

---

Bestimme eine äquivalente Darstellung von
$\neg (p \implies q)$.

$$
\neg (p \implies q)
$$
$$
= \neg(\neg p \lor q)
$$
$$
= \neg (\neg p) \land (\neg q)
$$
$$
= p \land (\neg q)
$$

### Negation

**Beispiel:**

$P$: Alle Schafe sind weiß

$\neg P$: Nicht alle Schafe sind weiß. Es gibt Schafe, die nicht weiß sind. Mindestens ein Schaf ist nicht weiß.

### Konjunktion

Für logische Aussagen p, q und r gelten die folgenden Regeln:

* Kommutativgesetz der Konjunktion

$$
p \land q = q \land p
$$

* Assoziativgesetz der Konjunktion

$$
(p \land q) \land r = p \land (q \land r)
$$

### Disjunktion

Das Kommutativgesetz und das Assoziativgesetz können analog zur Konjunktion angewendet werden.

#### Distributivgesetze von Konjunktion und Disjunktion

* Distributivgesetz 1:
$$
p \land (q \lor r) = (p \land q) \lor (p \land r)
$$

* Distributivgesetz 2:
$$
p \lor (q \land r) = (p \lor q) \land (p \lor r)
$$

> Auffällig ist hierbei die Ähnlichkeit zum Distributivgesetz von Addition und Multiplikation der reellen Zahlen.

**Beispiel:**

$$
a (b + c) = (a b) + (a c)
$$

#### Negation von Konjunktion bzw. Disjunktion

Durch die Negation von Konjunktion bzw. Disjunktion (bspw. durch eine Wahrheitstabelle) kommt man zu dem Schluss, dass

- $p \land q = \overline{p} \lor \overline{q}$
- $p \lor q = \overline{p} \land \overline{q}$

Diese beiden Schlüsse werden die *De Morgansche Gesetze* genannt.

### Implikation

Wahrheitstabelle für $p \implies q$:

|$p$|$q$|$p \implies q$|
|:-:|:-:|:------------:|
|$w$|$w$|$w$           |
|$f$|$w$|$w$           |
|$w$|$f$|$f$           |
|$f$|$f$|$w$           |

Die Implikation ist nur falsch, wenn p wahr ist und q falsch ist.

> In der Wahrheitswertetabelle sind inbesondere die beiden letzten Zeilen zu beachten, da sie für viele nicht intuitiv erscheinen.
> Sie beschreiben das Prinzip „ex falso sequitur quodlibet“, also „aus Falschem folgt Beliebiges“.
> Die Implikation $p \implies q$ ist für eine falsche Aussage $p$ immer wahr, was allerdings nichts darüber aussagt, ob die Aussage $q$ wahr oder falsch ist.

> Sprachliche Bezeichnungen für $p \implies q$ sind:

> * aus $p$ folgt $q$
> * $p$ ist hinreichend für $q$
> * $q$ ist notwendig für $p$
> * wenn $p$, dann $q$

#### Ersetzung der Implikation

Für Aussagen $p$ und $q$ gilt stets die (logische) Gleichheit $p \implies q = \overline{p} \lor q$.

Die Herleitung dazu steht im Opal-Vorbereitungskurs.

---

#### Übung

Überprüfen Sie die logische Gleichheit der beiden Formeln $p \implies q$ und $\overline{q} \implies \overline{p}$, also die Kontraposition der Implikation, mithilfe einer Wahrheitswertetabelle.

|$p$|$q$|$p \implies q$|$\overline{q} \implies \overline{p}$|
|:-:|:-:|:------------:|:----------------------------------:|
|w  |w  |w             |w                                   |
|w  |f  |f             |f                                   |
|f  |w  |w             |w                                   |
|f  |f  |w             |w                                   |

### Äquivalenz

$p \iff q$ ist genau dann wahr, wenn $p$ und $q$ den gleichen Wahrheitswert besitzen.

#### Ersetzung der Äquivalenz durch Implikationen

$$
p \iff q = (p \implies q) \land (q \implies p)
$$


### Prädikate und Stellen eines Prädikats

**Beispiel:** *Die Funktion $f$ ist stetig.*

…ist keine Aussage, sondern ein Prädikat, weil über den Wahrheitsgehalt keine Aussage getroffen werden kann. $f$ muss dafür definiert werden.$

Ein *Lemma* ist ein Hilfssatz.

**Beispiel:** Prädikate

* 1 Stelle: Die Funktion $f$ ist stetig.
* 2 Stellen: $f$ hat in $x$ eine Nullstelle.
* 3 Stellen: $f$ ist stetig auf $[x_{1}, x_{2}]$.
* 0 Stellen: $100 = 10^{2}$

0-stellige Prädikate sind dementsprechend Aussagen.

Prädikat $P$ mit $x$ eingesetzt $P(x)$ ist eine Aussage.

### Existenzquantor und Allquantor

**Beispiel:** Aussagen mit Quantoren

Gegeben sei die Funktion f ∶ R → R mit f(x) = x2 − 1.
Finde Beispiele für Aussagen über die Funktion f mit Quantoren. Sind diese Aussagen wahr oder falsch?

* $f$ hat in $\R$ mindestens 2 Nullstellen. $\exists x_{1}, x_{2} \in \R \mid (x_{1} \ne x_{2})$
* $f$ ist auf ganz $\R$ definiert. $\forall x \in \R, \exists y \in \R \mid f(x)=y$
* $\forall x \in (0,) \mid f'(x) \gt 0$

HIER FEHLT ETWAS; s. Folien

### Negation von Quantoren

$P: \neg (\exists x \in \R \mid x^{x} = -1)$

= hier fehlt was :)

**Beispiel:** Negation von Quantoren

Formuliere die Aussage
*Es gibt keine reelle Zahl, deren Quadrat −1 ist*
mit Hilfe von Quantoren und löse die Negation auf.

$$
\nexists x : x \in \R : x^{2} = -1
$$

## Mengen und Elemente

**Beispiel:** Notation von Mengen

Gib die folgenden Mengen an:

(a) Die Menge aller geraden Zahlen zwischen 15 und 25.

$$
A = \Set{x|x \gt 15 \land x \lt 25 \land x \mod 2 = 0}
$$

(b) Die Menge aller nichtnegativen Zahlen, die kleiner als 3 sind.

$$
B = \Set{x|x \ge 0 \land x \lt 3}
$$

(c) Die Menge aller achsensymmetrischen Funktionen von R nach R.

*Hier bin ich mir selbst sicher, dass das so nicht stimmt.*

$$
C = \Set{x|\R \rightarrow \R \land f(-x) = f(x)}
$$

## Notizen für nach der Vorlesung

- *Warum ist die Implikation wahr und nicht falsch, wenn die Grundaussage $p$ falsch ist?*
