---
title: 'Bibliothèques standard Q #-structures de données | Microsoft Docs'
description: 'Bibliothèques standard Q #-structures de données'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 6eb47de84fdfbb9d35fdfc2988883f8e1cffa332
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864353"
---
# <a name="data-structures-and-modeling"></a>Structures de données et modélisation #

## <a name="classical-data-structures"></a>Structures de données classiques ##

Outre les types définis par l’utilisateur pour représenter les concepts de Quantum, Canon fournit également des opérations, des fonctions et des types pour l’utilisation des données classiques utilisées dans le contrôle des systèmes quantiques.
Par exemple, la fonction <xref:microsoft.quantum.arrays.reversed> prend un tableau comme entrée et retourne le même tableau dans l’ordre inverse.
Il peut ensuite être utilisé sur un tableau de type `Qubit[]` pour éviter d’avoir à appliquer des portes $ \operatorname{SWAP} $ inutiles lors de la conversion entre des représentations quantiques d’entiers.
De même, nous avons vu dans la section précédente que les types de formulaire `(Int, Int -> T)` peuvent être utiles pour représenter des collections d’accès aléatoires, donc la fonction <xref:microsoft.quantum.arrays.lookupfunction> offre un moyen pratique de construire de tels types à partir de types tableau.

### <a name="pairs"></a>Correspondre ###

Canon prend en charge la notation de style fonctionnel pour les paires, en complément de l’accès aux tuples par déconstruction :

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Tableaux ###

Canon fournit plusieurs fonctions pour manipuler des tableaux.
Ces fonctions sont paramétrées par type et peuvent donc être utilisées avec les tableaux de n’importe quel type Q #.
Par exemple, la fonction <xref:microsoft.quantum.arrays.reversed> retourne un nouveau tableau dont les éléments sont dans l’ordre inverse de son entrée.
Cela peut être utilisé pour modifier la façon dont un registre Quantum est représenté lors de l’appel d’opérations :

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

De même, la fonction <xref:microsoft.quantum.arrays.subarray> peut être utilisée pour réorganiser ou prendre des sous-ensembles des éléments d’un tableau :

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

Lorsqu’il est associé à un contrôle de Flow, les fonctions de manipulation de tableau comme <xref:microsoft.quantum.arrays.zip> peuvent offrir un moyen puissant d’exprimer des programmes Quantum :

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Oracle ##

Dans la documentation sur l' [estimation de phase](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) et l' [amplification d’amplitude](https://en.wikipedia.org/wiki/Amplitude_amplification) , le concept d’Oracle s’affiche fréquemment.
Ici, le terme Oracle fait référence à une sous-routine Quantum Blackbox qui agit sur un ensemble de qubits et renvoie la réponse en tant que phase.
Cette sous-routine peut souvent être considérée comme une entrée d’un algorithme Quantum qui accepte Oracle, en plus d’autres paramètres, et applique une série d’opérations de Quantum et traite un appel à cette sous-routine Quantum comme s’il s’agissait d’une porte fondamentale.
Évidemment, pour implémenter réellement le plus grand algorithme, une décomposition concrète d’Oracle en portes fondamentales doit être fournie, mais une telle décomposition n’est pas nécessaire pour comprendre l’algorithme qui appelle Oracle.
Dans Q #, cette abstraction est représentée à l’aide de ces opérations qui sont des valeurs de première classe, de telle sorte que les opérations peuvent être passées aux implémentations des algorithmes de Quantum en utilisant une boîte noire.
En outre, les types définis par l’utilisateur sont utilisés pour étiqueter les différentes représentations Oracle d’une manière sécurisée, ce qui rend difficile la déflation accidentelle de différents genres d’opérations de boîte noire.

Ces Oracle apparaissent dans plusieurs contextes différents, y compris des exemples célèbres, tels que les algorithmes [de recherche et de simulation de quantum de Grover](https://en.wikipedia.org/wiki/Grover%27s_algorithm) .
Ici, nous nous concentrons sur les Oracle requis pour deux applications seulement : amplification d’amplitude et estimation de phase.
Nous allons tout d’abord aborder les Oracle amplification d’amplitude avant de passer à l’estimation de phase.

### <a name="amplitude-amplification-oracles"></a>Amplification d’amplitude Oracle ###

L’algorithme d’amplification d’amplitude vise à effectuer une rotation entre un état initial et un état final en appliquant une séquence de réflexions de l’État.
Pour que l’algorithme fonctionne, il a besoin d’une spécification de ces deux États.
Ces spécifications sont fournies par deux Oracle.
Ces Oracle fonctionnent en séparant les entrées en deux espaces, un sous-espace « cible » et un sous-espace « initial ».
Les Oracle identifient de tels sous-espaces, de la même façon que les opérateurs Pauli identifient deux espaces, en appliquant une phase $ \pm $1 à ces espaces.
La principale différence réside dans le fait que ces espaces n’ont pas besoin d’être des demi-espaces dans cette application.
Notez également que ces deux sous-espaces ne sont généralement pas mutuellement exclusifs : il y aura des vecteurs qui sont membres des deux espaces.
Si ce n’est pas le cas, alors l’amplification d’amplitude n’aurait aucun effet. par conséquent, nous avons besoin du sous-espace initial pour avoir un chevauchement différent de zéro avec le sous-espace cible.

Nous désignerons la première Oracle dont nous avons besoin pour l’amplification de l’amplitude afin d’être $P\_$0, définie pour avoir l’action suivante.  Pour tous les États $ \ket{x} $ dans le sous-espace « initial » $P\_0 \ket{x} =-\ket{x} $ et pour tous les États $ \ket{y} $ qui ne sont pas dans ce sous-espace, nous avons $P\_0 \ket{y} = \ket{y} $.
L’Oracle qui marque le sous-espace cible, $P _ 1 $, prend exactement la même forme.
Pour tous les États $ \ket{x} $ dans le sous-espace cible (c’est-à-dire, pour tous les États que vous souhaitez que l’algorithme génère), $P _ 1 \ Ket {x} =-\ket{x} $.
De même, pour tous les États $ \ket{y} $ qui ne se trouvent pas dans le sous-espace cible $P _ 1 \ Ket {y} = \ket{y} $.
Ces deux réflexions sont ensuite combinées pour former un opérateur qui exerce une seule étape d’amplification de l’amplitude, $Q =-P_0 P_1 $, où le signe moins global est uniquement important à prendre en compte dans les applications contrôlées.
L’amplification d’amplitude se poursuit ensuite en prenant un état initial, $ \ket{\Psi} $ qui se trouve dans le sous-espace initial, puis exécute $ \ket{\Psi} \mapsto Q ^ m \ket{\Psi} $.
Le fait d’effectuer une telle itération garantit que si l’un d’eux commence par un état initial qui a le chevauchement $ \sin ^ 2 (\Theta) $ avec l’espace marqué, après $m $ iterations, ce chevauchement devient $ \sin ^ 2 ([2m + 1] \Theta) $.
Par conséquent, nous souhaitons généralement choisir $m $ comme un paramètre gratuit de sorte que $ [2m + 1] \Theta = \ pi/2 $; Toutefois, ces choix rigides ne sont pas aussi importants pour certaines formes d’amplification d’amplitude, telles que l’amplification d’amplitude à virgule fixe.
Ce processus nous permet de préparer un État dans le sous-espace marqué à l’aide de augmentera moins de requêtes à la fonction de marquage et de la fonction de préparation de l’État qu’il ne serait possible sur un appareil strictement classique.
C’est pourquoi l’amplification de l’amplitude est un bloc de construction significatif pour de nombreuses applications de quantum computing.

Pour comprendre comment utiliser l’algorithme, il est utile de fournir un exemple qui donne une construction d’Oracle.  Envisagez d’exécuter l’algorithme de Grover pour les recherches de base de données dans ce paramètre.
Dans la recherche de Grover, l’objectif est de transformer l’État $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket{0}$ dans l’un des États marqués (potentiellement).
Pour simplifier davantage, nous allons simplement examiner le cas où le seul État marqué est $ \ket{0}$.
Nous avons ensuite conçu deux oracles : un qui marque uniquement l’état initial $ \ket{+} ^ {\otimes n} $ avec un signe moins et un autre qui marque l’État marqué $ \ket{0}$ avec un signe moins.
La dernière porte peut être implémentée à l’aide de l’opération de traitement suivante, à l’aide des opérations de contrôle de workflow dans Canon :

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

Cet Oracle est ensuite un cas particulier de l’opération <xref:microsoft.quantum.canon.rall1>, qui permet une rotation par une phase arbitraire au lieu du cas de réflexion $ \Phi = \pi $.
Dans ce cas, `RAll1` est semblable à l’opération <xref:microsoft.quantum.intrinsic.r1> préambule destiné à, dans le fait qu’il pivote à propos de $ \ket{11\cdots1} $ au lieu de l’État qubit $ \ket{1}$.

L’Oracle qui marque le sous-espace initial peut être construit de la même manière.
En pseudo-code :

1. Appliquez $H $ Gates à chaque qubit.
2. Appliquez $X $ Gates à chaque qubit.
3. Appliquez un $n-$1 contrôlé $Z $-Gate à la $n ^ {\text{th}} $ qubit.
4. Appliquez $X $ Gates à chaque qubit.
5. Appliquez $H $ Gates à chaque qubit.

Cette fois-ci, nous vous présenterons également l’utilisation de <xref:microsoft.quantum.canon.applywith> avec l’opération <xref:microsoft.quantum.canon.rall1> décrite ci-dessus :

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

Nous pouvons ensuite combiner ces deux oracles ensemble pour faire pivoter les deux États et transformer de manière déterministe $ \ket{+} ^ {\otimes n} $ en $ \ket{0}$ à l’aide d’un certain nombre de couches de portes Hadarmard qui est proportionnel à $ \sqrt{2 ^ n} $ (IE $m \propto \sqrt{2 ^ n} $) par rapport aux couches $2 ^ n $ environ qui seraient nécessaires pour préparer de manière non déterministe l’État $ \ket{0}$ en préparant et mesurant l’état initial jusqu’à ce que le résultat $0 $ soit respecté.

### <a name="phase-estimation-oracles"></a>Estimation de phase Oracle ###

Pour l’estimation de phase, les Oracle sont un peu plus naturels.
L’objectif de la phase d’estimation de la phase est de concevoir une sous-routine capable d’effectuer un échantillonnage à partir du valeurs propres d’une matrice d’unités.
Cette méthode est indispensable dans la simulation quantique car, pour de nombreux problèmes physiques dans la chimie et la science de la matériel, ces valeurs propres offrent les énergies de l’état de masse des systèmes quantiques qui nous fournissent des informations précieuses sur les diagrammes de phase de matériaux et dynamique de réaction pour les molécules.
Chaque version d’estimation de phase a besoin d’une unité d’entrée.
Cette unité est habituellement décrite par l’un des deux types d’Oracle.

> [!TIP]
> Les deux types Oracle décrits ci-dessous sont traités dans les exemples.
> Pour en savoir plus sur les requêtes Oracle continues, consultez l' [exemple **PhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation).
> Pour en savoir plus sur les requêtes discrètes Oracle, consultez l' [exemple **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

Le premier type d’Oracle, que nous appelons une requête discrète Oracle et qui représente le type défini par l’utilisateur <xref:microsoft.quantum.oracles.discreteoracle>, implique simplement une matrice d’unités.
Si $U $ est l’unité de valeurs propres que nous souhaitons estimer, alors Oracle for $U $ est simplement une solution de secours pour une sous-routine qui implémente $U $.
Par exemple, il peut s’agir $U $ comme Oracle $Q $ défini ci-dessus pour l’estimation de l’amplitude.
Le valeurs propres de cette matrice peut être utilisé pour estimer le chevauchement entre les États initial et cible, $ \sin ^ 2 (\Theta) $, en utilisant augmentera moins d’échantillons que l’un d’eux n’en aurait besoin autrement.
Cela a pour avantage l’application d’une estimation de phase utilisant Grover Oracle $Q $ comme entrée du moniker de l’estimation de l’amplitude.
Une autre application courante, largement utilisée dans la métrologie quantique, implique l’estimation d’un petit angle de rotation.
En d’autres termes, nous souhaitons estimer $ \Theta $ pour une porte de rotation inconnue de la forme $R _z (\Theta) $.
Dans ce cas, la sous-routine avec laquelle nous interagissons afin d’obtenir cette valeur fixe de $ \Theta $ pour la porte est $ $ \begin{align} U & = R_z (\Theta) \\\\ & = \begin{bmatrix} e ^ {-i \Theta/2} & 0 \\\\ 0 & e ^ {i/Theta/2} \end{bmatrix}.
\end{align} $ $

Le deuxième type d’Oracle utilisé dans l’estimation de la phase est la requête continue Oracle, représentée par le type de <xref:microsoft.quantum.oracles.continuousoracle>.
Une requête continue Oracle for phase estimation prend la forme $U (t) $ où $t $ est un nombre réel connu.
Si nous laissons $U $ être une unité fixe, la requête continue Oracle prend la forme $U (t) = U ^ t $.
Cela nous permet d’interroger des matrices telles que $ \sqrt{U} $, qui n’ont pas pu être implémentées directement dans le modèle de requête discret.

Ce type d’Oracle est utile lorsque vous n’êtes pas en train de sonder une unité particulière, mais que vous souhaitez plutôt apprendre les propriétés du générateur de l’unité.
Par exemple, dans la simulation de Quantum dynamique, l’objectif est de concevoir des circuits quantiques qui se rapprochent $U (t) = e ^ {-i H t} $ pour une matrice Hermitian $H $ et l’heure d’évolution $t $.
Le valeurs propres de $U (t) $ est directement lié au valeurs propres de $H $.
Pour voir cela, considérez un extraction de $H $ : $H \ket{E} = E\ket {E} $, puis il est facile de voir la définition de la série Power de la matrice exponentielle qui $U (t) \ket{E} = e ^ {i\phi} \ Ket {E} = e ^ {-iEt} \ket{E} $.
Par conséquent, l’estimation de la eigenphase de $U (t) $ donne au eigenvalue $E $ en supposant que le extraction $ \ket{E} $ est entré dans l’algorithme d’estimation de la phase.
Toutefois, dans ce cas, la valeur $t $ peut être choisie à la discrétion de l’utilisateur, car pour toute valeur suffisamment faible de $t $ eigenvalue $E $ peut être inversée de manière unique via $E =-\ Phi/t $.
Étant donné que les méthodes de simulation quantique offrent la possibilité d’effectuer une évolution fractionnaire, les algorithmes d’estimation de phase allocations sont une liberté supplémentaire lors de l’interrogation de l’unité, en particulier lorsque le modèle de requête discret autorise uniquement les unités de la forme $U ^ j $ à appliquer pour les entiers $j $ la requête continue Oracle nous permet d’obtenir des unités approximatives de la forme $U ^ t $ pour toute valeur réelle $t $.
Il est important de s’assurer que chaque dernière onces d’efficacité est un algorithme d’estimation hors phase, car cela nous permet de choisir précisément l’expérience qui fournirait le plus d’informations sur $E $; tandis que les méthodes basées sur des requêtes discrètes doivent faire l’intérêt d’une compromission en choisissant le meilleur nombre entier de requêtes dans l’algorithme.

En guise d’exemple concret, considérez le problème d’estimation non de l’angle de rotation d’une porte, mais la fréquence procession d’un système Quantum tournant.
L’unité qui décrit cette dynamique quantique est $U (t) = R_z (2 \ Omega t) $ pour l’heure d’évolution $t $ et la fréquence inconnue $ \omega $.
Dans ce contexte, nous pouvons simuler $U (t) $ pour n’importe quel $t $ à l’aide d’une seule $R _z $ Gate et, par conséquent, n’ont pas besoin de se limiter à des requêtes discrètes à l’unité.
Un tel modèle continu a également la propriété dont les fréquences supérieures à $2 \ pi $ peuvent être apprises dans les processus d’estimation de phase qui utilisent des requêtes continues, car les informations de phase qui seraient autrement masquées par les coupes de la fonction logarithmique peuvent être dévoilées à partir des résultats des expérimentations effectuées sur des valeurs non proportionnées de $t $.
Ainsi, pour les problèmes tels que les modèles de requête continues pour l’estimation de phase Oracle, ils sont non seulement appropriés, mais ils sont également préférables au modèle de requête discret.
Pour cette raison, Q # a des fonctionnalités pour les deux formes de requêtes et laisse l’utilisateur décider d’un algorithme d’estimation de la phase en fonction de ses besoins et du type d’Oracle disponible.

## <a name="dynamical-generator-modeling"></a>Modélisation de générateurs dynamiques ##

Les générateurs de temps-évolution décrivent comment les États évoluent dans le temps. Par exemple, la dynamique d’un État Quantum $ \ket{\Psi} $ est régie par l’équation Schrödinger $ $ \begin{align} i\frac {d \ket{\Psi (t)}} {d t} & = H \ket{\Psi (t)}, \end{align} $ $ avec une matrice Hermitian $H $, appelée « Hamilton », comme générateur de films. Étant donné un état initial $ \ket{\Psi (0)} $ à temps $t = $0, la solution formelle à cette équation $t $ peut être, en principe, écrite $ $ \begin{align} \ket{\Psi (t)} = U (t) \ket{\Psi (0)}, \end{align} $ $ où la matrice exponentielle $U (t) = e ^ {-i H t} $ est appelée opérateur d’évolution temporelle. Bien que nous nous concentrons sur les générateurs de ce formulaire dans ce qui suit, nous insistons sur le fait que le concept s’applique plus largement, par exemple à la simulation de systèmes quantiques ouverts, ou à des équations différentielles plus abstraites.

L’objectif principal de la simulation dynamique est d’implémenter l’opérateur de l’évolution temporelle sur un État Quantum encodé dans qubits d’un ordinateur quantique.  Dans de nombreux cas, la partie Hamilton peut être divisée en une somme de quelques termes $d $ plus simples

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

où l’évolution du temps par chaque terme est facile à implémenter sur un ordinateur quantique. Par exemple, si $H _j $ est un Pauli $X _1X_2 $ Operator agissant sur les 1er et 2e éléments du Registre qubit `qubits`, Time-Evolution pour chaque fois $t $ peut être implémenté simplement en appelant l’opération `Exp([PauliX,PauliX], t, qubits[1..2])`, qui a une `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`de signature. Comme nous l’avons vu plus loin dans la simulation de la version Hamilton, une solution consiste à évaluer l’évolution du temps en $H $ avec une séquence d’opérations plus simples.

$ $ \begin{align} U (t) & = \left (e ^ {-u\_0 t/r} e ^ {--1\_1 t/r} \cdots e ^ {-m-m\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\| H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $

où l’entier $r > $0 contrôle l’erreur d’approximation.

La bibliothèque de modélisation de générateurs dynamiques fournit une infrastructure pour l’encodage systématique des générateurs complexes en termes de générateurs plus simples. Une telle description peut ensuite être transmise à, par exemple, la bibliothèque de simulation pour implémenter l’évolution du temps par un algorithme de simulation de choix, avec de nombreux détails automatiquement pris en charge.

> [!TIP]
> La bibliothèque de générateurs dynamiques décrite ci-dessous est traitée dans les exemples. Pour obtenir un exemple basé sur le modèle Ising, consultez l' [exemple **IsingGenerators** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/generators).
> Pour obtenir un exemple basé sur l’hydrogène moléculaire, consultez les exemples [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) et [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/gui) .

### <a name="complete-description-of-a-generator"></a>Description complète d’un générateur ###

Au niveau supérieur, une description complète d’un type de type Hamilton est contenue dans le `EvolutionGenerator` type défini par l’utilisateur qui a deux composants :

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

Le type de `GeneratorSystem` défini par l’utilisateur est une description classique de l’un des.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

Le premier élément `Int` du tuple stocke le nombre de termes $d $ dans l’un des deux, et le deuxième élément `(Int -> GeneratorIndex)` est une fonction qui mappe un index d’entiers dans $\{0, 1,..., d-1\}$ à un type défini par l’utilisateur `GeneratorIndex` qui identifie de façon unique chaque terme primitif dans le lieu de la communauté. Notez qu’en exprimant la collection de termes dans la « Hamilton » en tant que fonction plutôt qu’en tant que tableau `GeneratorIndex[]`, cela permet le calcul à la volée du `GeneratorIndex` qui est particulièrement utile lors de la description de Hamiltonians avec un grand nombre de termes.

Pour l’essentiel, nous n’avons pas imposé de Convention sur les termes primitifs identifiés par les `GeneratorIndex` sont faciles à simuler. Par exemple, les termes primitifs peuvent être des opérateurs Pauli comme indiqué ci-dessus, mais ils peuvent également être Fermionic annihilation et des opérateurs de création couramment utilisés dans la simulation de chimie quantique. En soi, un `GeneratorIndex` n’a pas de sens, car il ne décrit pas comment l’évolution temporelle du terme vers laquelle il pointe peut être implémentée en tant que circuit quantique.

Cela est résolu en spécifiant un `EvolutionSet` type défini par l’utilisateur qui mappe tout `GeneratorIndex`, dessiné à partir d’un ensemble canonique, à un opérateur unitaire, le `EvolutionUnitary`, exprimé comme un circuit quantique. L' `EvolutionSet` définit la Convention de la structure d’un `GeneratorIndex` et définit également l’ensemble des `GeneratorIndex`possibles.

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Générateurs d’opérateur Pauli ###

Un exemple concret et utile de générateurs est un Hamiltonians qui est une somme d’opérateurs Pauli, chacun pouvant avoir un coefficient différent.
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j, \end{align} $ $ où chaque $ \hat H_j $ est désormais extraite du groupe Pauli. Pour ces systèmes, nous fournissons le `PauliEvolutionSet()` de type `EvolutionSet` qui définit une convention pour la façon dont un élément du groupe Pauli et un coefficient peuvent être identifiés par un `GeneratorIndex`, qui a la signature suivante.

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

Dans notre encodage, le premier paramètre `Int[]` spécifie une chaîne Pauli, où $ \hat I\rightarrow $0, $ \hat X\rightarrow $1, $ \hat Y\rightarrow $2 et $ \hat Z\rightarrow $3. Le deuxième paramètre `Double[]` stocke le coefficient de la chaîne Pauli dans le lieu de la même-Hamilton. Notez que seul le premier élément de ce tableau est utilisé. Le troisième paramètre `Int[]` indexe le qubits sur lequel cette chaîne Pauli agit, et ne doit pas avoir d’éléments en double. Ainsi, le terme de Hamilton $0,4 \hat X_0 \hat Y_8 \hat I_2 Z_1 \hat $ peut être représenté comme

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

Le `PauliEvolutionSet()` est une fonction qui mappe n’importe quel `GeneratorIndex` de ce formulaire à un `EvolutionUnitary` avec la signature suivante.

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

Le premier paramètre représente une durée, qui sera multiplié par le coefficient dans le `GeneratorIndex`, de l’évolution unitaire. Le deuxième paramètre est le qubit inscrit sur lequel agit l’unité. 

### <a name="time-dependent-generators"></a>Générateurs dépendants du temps ###

Dans de nombreux cas, nous sommes également intéressés par la modélisation des générateurs dépendants du temps, comme cela peut se produire dans l’équation Schrödinger $ $ \begin{align} i\frac {d \ket{\Psi (t)}} {d t} & = \hat H (t) \ket{\Psi (t)}, \end{align} $ $ où le générateur $ \hat H (t) $ est désormais dépend du temps. L’extension des générateurs indépendants du temps ci-dessus à ce cas est simple. Plutôt que d’avoir un `GeneratorSystem` fixe décrivant la Hamilton pour toutes les heures $t $, nous avons plutôt le `GeneratorSystemTimeDependent` type défini par l’utilisateur.

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

Le premier paramètre est un paramètre de planification continue $s \Dans [0, 1] $, et les fonctions de ce type retournent une `GeneratorSystem` pour cette planification. Notez que le paramètre de planification peut être lié de manière linéaire au paramètre de temps physique, par exemple $s = t/T $, pour une durée totale de simulation $T $. Toutefois, cela n’est pas nécessairement le cas.

De même, une description complète de ce générateur requiert une `EvolutionSet`et, par conséquent, nous définissons un type `EvolutionSchedule` défini par l’utilisateur.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
