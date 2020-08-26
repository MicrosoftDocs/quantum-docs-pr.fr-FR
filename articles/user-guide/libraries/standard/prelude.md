---
title: Opérations et fonctions intrinsèques dans QDK
description: En savoir plus sur les opérations et les fonctions intrinsèques dans le QDK, y compris les fonctions classiques et les opérations d’unité, de rotation et de mesure.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4eb10e82a64381c503703be440be90e60f3a8622
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863723"
---
# <a name="the-prelude"></a>Préambule destiné à #

Le Q# compilateur et les ordinateurs cibles inclus avec le kit de développement Quantum fournissent un ensemble de fonctions et d’opérations intrinsèques qui peuvent être utilisées lors de l’écriture de programmes de Quantum dans Q# .

## <a name="intrinsic-operations-and-functions"></a>Opérations et fonctions intrinsèques ##

Les opérations intrinsèques définies dans la bibliothèque standard appartiennent approximativement à l’une des catégories suivantes :

- Fonctions classiques essentielles, collectées dans l' <xref:microsoft.quantum.core> espace de noms.
- Opérations représentant des unités de [Clifford et de $T $ Gates](xref:microsoft.quantum.concepts.qubit).
- Opérations représentant des rotations sur différents opérateurs.
- Opérations mettant en œuvre des mesures.

Étant donné que l’ensemble de portes Clifford + $T $ est [universel](xref:microsoft.quantum.concepts.multiple-qubits) pour le quantum computing, ces opérations suffisent à implémenter n’importe quel algorithme Quantum dans une petite erreur negligibly.
En fournissant également des rotations, Q# permet au programmeur de travailler au sein de la bibliothèque qubit Unity et cnotin Gate unique. Cette bibliothèque est beaucoup plus facile à réfléchir, car elle ne nécessite pas que le programmeur n’exprime directement la décomposition Clifford + $T $ et que des méthodes très efficaces existent pour compiler des unités qubit uniques dans Clifford et $T $ Gates (voir [ici](xref:microsoft.quantum.more-information) pour plus d’informations).

Dans la mesure du possible, les opérations définies dans le préambule destiné à qui agissent sur qubits autorisent l’application de la `Controlled` variante, de telle sorte que l’ordinateur cible effectue la décomposition appropriée.

La plupart des fonctions et opérations définies dans cette partie du préambule destiné à se trouvent dans l' @"microsoft.quantum.intrinsic" espace de noms, de telle sorte que la plupart des Q# fichiers sources auront une `open Microsoft.Quantum.Intrinsic;` directive immédiatement après la déclaration d’espace de noms initiale.
L' <xref:microsoft.quantum.core> espace de noms s’ouvre automatiquement, de sorte que les fonctions telles que <xref:microsoft.quantum.core.length> peuvent être utilisées sans `open` instruction.

### <a name="common-single-qubit-unitary-operations"></a>Opérations courantes d’unités qubit simples ###

Préambule destiné à définit également de nombreuses [opérations courantes à qubit unique](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).
Toutes ces opérations autorisent à la fois les `Controlled` `Adjoint` functors et.

#### <a name="pauli-operators"></a>Pauli, opérateurs ####

L' <xref:microsoft.quantum.intrinsic.x> opération implémente l’opérateur Pauli $X $.
C’est ce que l’on appelle parfois la `NOT` porte.
Il possède une signature `(Qubit => Unit is Adj + Ctl)` .
Il correspond à l’unité qubit unique :

\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % correctif : cela utilise actuellement le pirate quadwhack.
1 & 0 \end{bmatrix} \end{Equation}

L' <xref:microsoft.quantum.intrinsic.y> opération implémente l’opérateur Pauli $Y $.
Il possède une signature `(Qubit => Unit is Adj + Ctl)` .
Il correspond à l’unité qubit unique :

\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % correctif : cela utilise actuellement le quadwhack hack.
i & 0 \end{bmatrix} \end{Equation}

L' <xref:microsoft.quantum.intrinsic.z> opération implémente l’opérateur Pauli $Z $.
Il possède une signature `(Qubit => Unit is Adj + Ctl)` .
Il correspond à l’unité qubit unique :

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % corriger : utilise actuellement le quadwhack hack.
0 &-1 \end{bmatrix} \end{Equation}

Ci-dessous, nous voyons ces transformations mappées à la [sphère Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (l’axe de rotation dans chaque cas est surligné en rouge) :

![Opérations Pauli mappées sur la sphère Bloch](~/media/prelude_pauliBloch.png)

Il est important de noter que l’application du même portail Pauli deux fois au même qubit annule l’opération (car vous avez maintenant effectué une rotation complète de 2π (360 °) sur la surface vers la sphère Bloch, ce qui revient au point de départ). Cela nous amène à l’identité suivante :

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Cela peut être visualisé sur la sphère Bloch :

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Autre Cliffords à qubit unique ####

L' <xref:microsoft.quantum.intrinsic.h> opération implémente la porte hadarmard.
Cela Interchange les axes Pauli $X $ et $Z $ du qubit cible, de telle sorte que $H \ket {0} = \ket{+} \mathrel{ : =} (\ket {0} + \ket {1} )/\sqrt {2} $ et $H \ket{+} = \ket {0} $.
Il possède `(Qubit => Unit is Adj + Ctl)` une signature et correspond à l’unité qubit unique :

\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % correctif : cela utilise actuellement le piratage quadwhack.
1 &-1 \end{bmatrix} \end{Equation}

La porte Hadarmard est particulièrement importante, car elle peut être utilisée pour créer une superposition des États $ \ket {0} $ et $ \ket {1} $. Dans la représentation Bloch Sphere, il est plus facile de considérer cela comme une rotation de $ \ket{\Psi} $ autour de l’axe x par $ \pi $ radians ($ 180 ^ \circ $) suivi d’une rotation (dans le sens des aiguilles d’une montre) autour de l’axe y par $ \ pi/2 $ radians ($ 90 ^ \circ $) :

![Opération hadarmard mappée sur la sphère Bloch](~/media/prelude_hadamardBloch.png)

L' <xref:microsoft.quantum.intrinsic.s> opération implémente la porte de phase $S $.
Il s’agit de la racine carrée de la matrice de l’opération Pauli $Z $.
Autrement dit, $S ^ 2 = Z $.
Il possède `(Qubit => Unit is Adj + Ctl)` une signature et correspond à l’unité qubit unique :

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % corriger : utilise actuellement le quadwhack hack.
0 & \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Roulements ####

En plus des opérations Pauli et Clifford ci-dessus, le Q# préambule destiné à fournit diverses façons d’exprimer des rotations.
Comme décrit dans [opérations à qubit unique](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), la possibilité d’effectuer une rotation est essentielle aux algorithmes Quantum.

Nous commençons par rappeler que nous pouvons exprimer une opération à qubit unique à l’aide de la $H $ et $T $ Gates, où $H $ est l’opération Hadarmard, et où \begin{Equation} T \mathrel{ : =} \begin{bmatrix} 1 & 0 \\ \\ % corriger : cette valeur utilise actuellement le pirate Quad Back Whack.
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} il s’agit de la racine carrée de l' <xref:microsoft.quantum.intrinsic.s> opération, par exemple $T ^ 2 = S $.
Le $T $ Gate est à son tour implémenté par l' <xref:microsoft.quantum.intrinsic.t> opération, et possède la signature `(Qubit => Unit is Adj + Ctl)` , indiquant qu’il s’agit d’une opération d’unité sur un qubit unique.

Même si cela est en principe suffisant pour décrire une opération arbitraire à qubit unique, les différentes machines cibles peuvent avoir des représentations plus efficaces pour les rotations sur les opérateurs Pauli, de sorte que le préambule destiné à comprend de nombreuses façons de convienently exprimer ces rotations.
Le plus simple est l' <xref:microsoft.quantum.intrinsic.r> opération, qui implémente une rotation autour d’un axe Pauli spécifié, \Begin{Equation} R (\sigma, \Phi) \mathrel{ : =} \exp (-i \Phi \sigma/2), \end{Equation} où $ \sigma $ est un opérateur Pauli, $ \Phi $ est un angle et où $ \exp $ représente l’exponentiel de la matrice.
Elle possède une signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , où les deux premières parties de l’entrée représentent les arguments classiques $ \sigma $ et $ \Phi $ requis pour spécifier l’opérateur unitaire $R (\sigma, \Phi) $.
Nous pouvons appliquer partiellement $ \sigma $ et $ \Phi $ pour obtenir une opération dont le type est celui d’une unité qubit unique.
Par exemple, `R(PauliZ, PI() / 4, _)` a le type `(Qubit => Unit is Adj + Ctl)` .

> [!NOTE]
> L' <xref:microsoft.quantum.intrinsic.r> opération divise l’angle d’entrée par 2 et le multiplie par-1.
> Pour $Z $ rotations, cela signifie que $ \ket {0} $ eigenstate est pivoté par $-\Phi/$2 et que $ \ket {1} $ eigenstate est pivoté par $ \phi/$2, de sorte que le \ket $ eigenstate {1} $ est pivoté par $ \Phi $ par rapport au $ \ket {0} $ eigenstate.
>
> En particulier, cela signifie que `T` et `R(PauliZ, PI() / 8, _)` diffère uniquement par une [phase globale](xref:microsoft.quantum.glossary#global-phase)non pertinente.
> C’est la raison pour laquelle $T $ est parfois appelé $ \frac{\pi} {8} $-Gate.
>
> Notez également que la rotation autour `PauliI` applique simplement une phase globale de $ \Phi/$2. Ces phases ne sont pas pertinentes, comme dans [les documents conceptuels](xref:microsoft.quantum.concepts.qubit), elles sont pertinentes pour les `PauliI` rotations contrôlées.

Dans les algorithmes Quantum, il est souvent utile d’exprimer des rotations en tant que fractions dyadic, de sorte que $ \Phi = \pi k/2 ^ n $ pour certains $k \Dans \mathbb{Z} $ et $n \Dans \mathbb{N} $.
L' <xref:microsoft.quantum.intrinsic.rfrac> opération implémente une rotation autour d’un axe Pauli spécifié à l’aide de cette Convention.
Il diffère de <xref:microsoft.quantum.intrinsic.r> en ce que l’angle de rotation est spécifié sous la forme de deux entrées de type `Int` , interprétées comme une fraction dyadic.
Par conséquent, `RFrac` possède une signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .
Il implémente le qubit unitaire $ \exp (i \pi k \sigma/2 ^ n) $, où $ \sigma $ est la matrice Pauli correspondant au premier argument, $k $ est le deuxième argument et $n $ est le troisième argument.
`RFrac(_,k,n,_)` est le même que `R(_,-πk/2^n,_)` ; Notez que l’angle est la valeur *négative* de la fraction.

L' <xref:microsoft.quantum.intrinsic.rx> opération implémente une rotation autour de Pauli $X $ Axis.
Il possède une signature `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rx(_, _)` est identique à `R(PauliX, _, _)`.

L' <xref:microsoft.quantum.intrinsic.ry> opération implémente une rotation autour de Pauli $Y $ Axis.
Il possède une signature `((Double, Qubit) => Unit is Adj + Ctl)` .
`Ry(_, _)` est identique à `R(PauliY,_ , _)`.

L' <xref:microsoft.quantum.intrinsic.rz> opération implémente une rotation autour de Pauli $Z $ AXIS.
Il possède une signature `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rz(_, _)` est identique à `R(PauliZ, _, _)`.

L' <xref:microsoft.quantum.intrinsic.r1> opération implémente une rotation par le montant donné autour de $ \ket {1} $, le eigenstate $-$1 de $Z $.
Il possède une signature `((Double, Qubit) => Unit is Adj + Ctl)` .
`R1(phi,_)` est le même que celui `R(PauliZ,phi,_)` suivi par `R(PauliI,-phi,_)` .

L' <xref:microsoft.quantum.intrinsic.r1frac> opération implémente une rotation fractionnaire en fonction de la valeur indiquée autour de Z = 1 eigenstate.
Il possède une signature `((Int,Int, Qubit) => Unit is Adj + Ctl)` .
`R1Frac(k,n,_)` est le même que celui `RFrac(PauliZ,-k.n+1,_)` suivi par `RFrac(PauliI,k,n+1,_)` .

Voici un exemple d’opération de rotation (autour du Pauli $Z $ AXIS, dans cette instance) mappée sur la sphère Bloch :

![Opération de rotation mappée sur la sphère Bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Opérations à plusieurs qubit ####

En plus des opérations qubit ci-dessus, le préambule destiné à définit également plusieurs opérations à plusieurs qubit.

Tout d’abord, l' <xref:microsoft.quantum.intrinsic.cnot> opération effectue une porte contrôlée standard `NOT` , \begin{Equation} \operatorname{CNOT} \mathrel{ : =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}.
\end{Equation} possède une signature `((Qubit, Qubit) => Unit is Adj + Ctl)` , représentant que $ \operatorname{CNOT} $ agit unitarily sur deux qubits individuels.
`CNOT(q1, q2)` est identique à `(Controlled X)([q1], q2)`.
Étant donné que le `Controlled` functor permet le contrôle sur un registre, nous utilisons le littéral `[q1]` de tableau pour indiquer que nous voulons uniquement le contrôle.

L' <xref:microsoft.quantum.intrinsic.ccnot> opération exécute une porte non contrôlée par doublement, parfois également appelée porte Toffoli.
Il possède une signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .
`CCNOT(q1, q2, q3)` est identique à `(Controlled X)([q1, q2], q3)`.

L' <xref:microsoft.quantum.intrinsic.swap> opération permute les États de quantum de deux qubits.
Autrement dit, il implémente la matrice \begin{Equation} \operatorname{SWAP} \mathrel{ : =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{Equation} possède une signature `((Qubit, Qubit) => Unit is Adj + Ctl)` .
`SWAP(q1,q2)` est équivalent à `CNOT(q1, q2)` suivi de `CNOT(q2, q1)` , puis `CNOT(q1, q2)` .

> [!NOTE]
> La porte d’échange n’est *pas* la même que la réorganisation des éléments d’une variable de type `Qubit[]` .
> L’application `SWAP(q1, q2)` de entraîne une modification de l’état du qubits référencé par `q1` et `q2` , tout en `let swappedRegister = [q2, q1];` affectant uniquement la manière dont nous faisons référence à ces qubits.
> En outre, `(Controlled SWAP)([q0], (q1, q2))` permet `SWAP` à d’être conditionné sur l’état d’un troisième qubit, que nous ne pouvons pas représenter en réorganisant les éléments.
> La porte contrôlée par échange, également appelée porte Fredkin, est suffisamment puissante pour inclure tous les calculs classiques.

Enfin, le préambule destiné à fournit deux opérations pour représenter des exponentiels d’opérateurs Pauli à plusieurs qubit.
L' <xref:microsoft.quantum.intrinsic.exp> opération effectue une rotation basée sur un produit tenseur de matrices Pauli, comme représenté par le qubit unitaire \Begin{Equation} \operatorname{exp} (\vec{\sigma}, \Phi) \mathrel{ : =} \exp\left (i \Phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} où $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ est une séquence d’opérateurs qubit Pauli, et où $ \Phi $ est un angle.
La `Exp` rotation représente $ \vec{\sigma} $ sous la forme d’un tableau d' `Pauli` éléments, de sorte qu’elle possède une signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .

L' <xref:microsoft.quantum.intrinsic.expfrac> opération effectue la même rotation, à l’aide de la notation de fraction dyadic décrite ci-dessus.
Il possède une signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .

> [!WARNING]
> Les exponentiels du produit tenseur des opérateurs Pauli ne sont pas les mêmes que les produits tenseur des exponentiels des opérateurs Pauli.
> Autrement dit, $e ^ {i (Z \otimes Z) \Phi} \ne e ^ {i Z \Phi} \otimes e ^ {i Z \Phi} $.

### <a name="measurements"></a>Mesures ###

Lors de la mesure, le + 1 eigenvalue de l’opérateur mesuré correspond à un `Zero` résultat, et le-1 eigenvalue à un `One` résultat.

> [!NOTE]
> Bien que cette Convention puisse paraître étrange, elle présente deux avantages très intéressants.
> Tout d’abord, l’observation du résultat $ \ket {0} $ est représentée par la `Result` valeur `Zero` , tandis que l’observation de $ \ket {1} $ correspond à `One` .
> Deuxièmement, nous pouvons écrire que le eigenvalue $ \lambda $ correspondant à un résultat $r $ est $ \lambda = (-1) ^ r $.

Les opérations de mesure ne prennent en charge ni le `Adjoint` functor ni le `Controlled` functor.

L' <xref:microsoft.quantum.intrinsic.measure> opération effectue une mesure conjointe d’un ou plusieurs qubits dans le produit spécifié des opérateurs Pauli.
Si le tableau Pauli et le tableau qubit ont des longueurs différentes, l’opération échoue.
`Measure` a une signature `((Pauli[], Qubit[]) => Result)` .

Notez qu’une mesure conjointe n’est pas identique à la mesure individuelle de chaque qubit.
Par exemple, considérez l’État $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.
En mesurant $Z _0 $ et $Z _ 1 $ chaque individuellement, nous obtenons les résultats $r _0 = $1 et $r _ 1 = $1.
En mesurant $Z _0 Z_1 $, nous obtenons le résultat unique $r _ {\textrm{joint}} = $0, ce qui indique que la paire de $ \ket {11} $ est positive.
Put différemment, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $.
En effet, étant donné que nous ne prenons en compte *que* la parité de cette mesure, toutes les informations de Quantum représentées dans la superposition entre les États 2 2-qubit de parité positive, $ \ket {00} $ et $ \ket {11} $, sont conservées.
Cette propriété sera essentielle plus tard, car nous aborderons la correction des erreurs.

Pour plus de commodité, le préambule destiné à fournit également deux autres opérations pour mesurer qubits.
Tout d’abord, étant donné que l’exécution de mesures qubit simples est assez courante, préambule destiné à définit un raccourci pour ce cas.
L' <xref:microsoft.quantum.intrinsic.m> opération mesure l’opérateur Pauli $Z $ sur un qubit unique et possède une signature `(Qubit => Result)` .
`M(q)` équivaut à `Measure([PauliZ], [q])`.

Le <xref:microsoft.quantum.measurement.multim> mesure le Pauli $Z $ Operator *séparément* sur chacun d’un tableau de qubits, en retournant le *tableau* de `Result` valeurs obtenues pour chaque qubit.
Dans certains cas, cela peut être optimisé. Il possède une signature ( `Qubit[] => Result[])` .
`MultiM(qs)` équivaut à :

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Fonctions et opérations d’extension ##

En outre, préambule destiné à définit un ensemble complet de fonctions mathématiques et de conversion de type au niveau du .NET pour une utilisation dans le Q# code.
Par exemple, l' <xref:microsoft.quantum.math> espace de noms définit des opérations utiles telles que <xref:microsoft.quantum.math.sin> et <xref:microsoft.quantum.math.log> .
L’implémentation fournie par le kit de développement quantum utilise la bibliothèque de classes de base .NET classique et peut donc impliquer un aller-retour supplémentaire entre les programmes Quantum et leurs pilotes classiques.
Bien que cela ne présente pas de problème pour un simulateur local, il peut s’agir d’un problème de performances lors de l’utilisation d’un simulateur distant ou d’un matériel réel comme ordinateur cible.
Cela dit, un ordinateur cible individuel peut atténuer cet impact sur les performances en remplaçant ces opérations par des versions qui sont plus efficaces pour ce système particulier.

### <a name="math"></a>Math ###

L' <xref:microsoft.quantum.math> espace de noms fournit de nombreuses fonctions utiles à partir de la [ `System.Math` classe](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)de la bibliothèque de classes de base .net.
Ces fonctions peuvent être utilisées de la même façon que toute autre Q# fonction :

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Quand une méthode statique .NET a été surchargée en fonction du type de ses arguments, la Q# fonction correspondante est annotée avec un suffixe indiquant le type de son entrée :

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Opérations au niveau du bit ###

Enfin, l' <xref:microsoft.quantum.bitwise> espace de noms fournit plusieurs fonctions utiles pour manipuler des entiers à l’aide d’opérateurs au niveau du bit.
Par exemple, <xref:microsoft.quantum.bitwise.parity> retourne la parité au niveau du bit d’un entier sous la forme d’un autre entier.
