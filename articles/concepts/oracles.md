---
title : description d’Oracle Quantum : Apprenez à utiliser et à définir des opérations de boîte noire à l’aide d’Oracle Quantum, qui sont utilisées comme entrée d’un autre algorithme.
Auteur : cgranade UID : Microsoft. Quantum. concepts. Oracle ms. Author : Christopher.Granade@microsoft.com ms. Date : 07/11/2018 ms. topic : article No-Loc :
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---
# <a name="quantum-oracles"></a>Oracle Quantum

Oracle $ O $ est une opération « boîte noire » utilisée comme entrée d’un autre algorithme.
Ces opérations sont souvent définies à l’aide d’une fonction classique $ f : \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ qui prend une $ $ entrée binaire n bits et produit $ une $ sortie binaire m bits.
Pour ce faire, considérons une entrée binaire particulière $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .
Nous pouvons étiqueter les États qubit sous la forme $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .

Nous pouvons tenter d’abord de définir $ o $ afin que $ o \ket { x } = \ket { f (x) } $ , mais cela pose quelques problèmes.
Premièrement, $ f $ peut avoir une taille différente d’entrée et de sortie ( $ n \ne m $ ), de sorte que l’application de $ O $ modifie le nombre de qubits dans le registre.
Deuxièmement, même si $ n = m $ , la fonction ne peut pas être réversible : si $ f (x) = f (y) $ pour un $ x \ne y $ , puis $ o \ket { x } = o \ket { y } $ mais $ o ^ \dagger o \ket { x } \ne o ^ \dagger o \ket { y } $ .
Cela signifie que nous ne pourrons pas construire l’opération voisine $ O ^ \dagger $ et qu’Oracle doit avoir un voisin défini pour eux.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Définition d’Oracle par son effet sur les États de base de calcul
Nous pouvons traiter ces deux problèmes en introduisant un deuxième Registre de $ m $ qubits pour y répondre.
Nous allons ensuite définir l’effet de l’Oracle sur tous les États de base de calcul : pour tous les États $ x \in \\ { 0, 1 \\ } ^ n $ et $ y \in \\ { 0, 1 \\ } ^ m $ ,

$$
\begin{align}
    O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .
\end{align}
$$

Maintenant $ o = o ^ \dagger $ par construction, nous avons résolu les deux problèmes précédents.

> [!TIP]
>Pour voir si $ o = o ^ { \dagger } $ , Notez que $ o ^ 2 = \boldone $ depuis $ un \oplus b \oplus b = a $ pour tout $ a, b \in \: :: No-Loc ({) ::: 0, 1 \: :: No-Loc (}) ::: $ .
>Par conséquent, $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .

Plus important encore, la définition d’une Oracle de cette façon pour chaque État de base de calcul $ \ket { x } \ket { y } $ définit également la manière dont $ O $ agit pour tout autre État.
Cela vient immédiatement du fait que $ O $ , comme toutes les opérations de Quantum, est linéaire dans l’État sur lequel il agit.
Examinez l’opération hadarmard, par exemple, qui est définie par $ h \ket { 0 } = \ket { + } $ et $ h \ket { 1 } = \ket { - } $ .
Si nous souhaitons savoir comment $ h $ agit sur $ \ket { + } $ , nous pouvons utiliser le $ h comme $ linéaire,

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\
           &= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .
\end{align}
$$

Dans le cas de la définition de notre $ O Oracle $ , nous pouvons utiliser de la même façon que n’importe quel état $ \ket { \psi } $ sur $ n + m $ qubits peut être écrit comme

$$
\begin{align}
\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}
\end{align}
$$

où $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ représente les coefficients de l’état $ \ket { \psi } $ . Donc

$$
\begin{align}
O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .
\end{align}
$$

## <a name="phase-oracles"></a>Oracle phase
Vous pouvez également encoder $ f $ dans une $ O Oracle $ en appliquant une _phase_ basée sur l’entrée à $ o $ . Par exemple, nous pouvons définir $ O de $ telle sorte que$$
\begin{align}
    O \ket { x } = (-1) ^ { f (x) } \ket { x } .
\end{align}
$$
Si une phase Oracle agit sur un registre initialement dans un état de base de calcul $ \ket { x } $ , cette phase est une phase globale qui n’est donc pas observable.
Toutefois, Oracle peut être une ressource très puissante si elle est appliquée à une superposition ou en tant qu’opération contrôlée.
Par exemple, considérez une phase Oracle $ O_f $ pour une fonction qubit unique $ $ .
Cliquez$$
\begin{align}
    O_f\ket{+}
        &=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\
        &=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .
\end{align}
$$

Plus généralement, les deux vues d’Oracle peuvent être élargies pour représenter des fonctions classiques qui retournent des nombres réels au lieu d’un seul bit.

Le choix de la meilleure façon d’implémenter Oracle dépend fortement de la façon dont ce Oracle sera utilisé dans un algorithme donné.
Par exemple, l' [algorithme Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) s’appuie sur Oracle implémenté de la même façon, tandis que l' [algorithme de Grover s'](https://en.wikipedia.org/wiki/Grover's_algorithm) appuie sur Oracle implémenté de la seconde façon.


Pour plus d’informations, nous vous suggérons la discussion dans [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
