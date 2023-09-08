+++
draft = false
aliases = ['']

title = 'Vorbereitungskurs Mathe Online Aussagenlogik'
subtitle = ''
topic = 'Aussagenlogik'
description = ''
summary = ''

semesters = 1
modules = 'Vorbereitungskurs Mathematik 2023 Online'
moduleNumber = ''

keywords = []

date = 2023-09-08T15:20:22+02:00
publishDate = 2023-09-08T15:20:22+02:00

includeToc = true
includeKaTeX = true
+++

## Konjunktion

Für logische Aussagen p, q und r gelten die folgenden Regeln:

* Kommutativgesetz der Konjunktion

$$
p \land q = q \land p
$$

* Assoziativgesetz der Konjunktion

$$
(p \land q) \land r = p \land (q \land r)
$$

## Disjunktion

Das Kommutativgesetz und das Assoziativgesetz können analog zur Konjunktion angewendet werden.

### Distributivgesetze von Konjunktion und Disjunktion

* Distributivgesetz 1:
$$
p \land (q \lor r) = (p \land q) \lor (p \land r)
$$

* Distributivgesetz 2:
$$
p \lor (q \land r) = (p \lor q) \land (p \lor r)
$$

> Auffällig ist hierbei die Ähnlichkeit zum Distributivgesetz von Addition und Multiplikation der reellen Zahlen.

Beispiel:

$$
a (b + c) = (a b) + (a c)
$$

### Negation von Konjunktion bzw. Disjunktion

Durch die Negation von Konjunktion bzw. Disjunktion (bspw. durch eine Wahrheitstabelle) kommt man zu dem Schluss, dass

- $p \land q = \overline{p} \lor \overline{q}$
- $p \lor q = \overline{p} \land \overline{q}$

Diese beiden Schlüsse werden die *De Morgansche Gesetze* genannt.

## Implikation

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

### Ersetzung der Implikation

Für Aussagen $p$ und $q$ gilt stets die (logische) Gleichheit $p \implies q = \overline{p} \lor q$.

Die Herleitung dazu steht im Opal-Vorbereitungskurs.

---

### Übung

Überprüfen Sie die logische Gleichheit der beiden Formeln $p \implies q$ und $\overline{q} \implies \overline{p}$, also die Kontraposition der Implikation, mithilfe einer Wahrheitswertetabelle.

|$p$|$q$|$p \implies q$|$\overline{q} \implies \overline{p}$|
|:-:|:-:|:------------:|:----------------------------------:|
|w  |w  |w             |w                                   |
|w  |f  |f             |f                                   |
|f  |w  |w             |w                                   |
|f  |f  |w             |w                                   |

## Äquivalenz

$p \iff q$ ist genau dann wahr, wenn $p$ und $q$ den gleichen Wahrheitswert besitzen.

### Ersetzung der Äquivalenz durch Implikationen

$$
p \iff q = (p \implies q) \land (q \implies p)
$$
