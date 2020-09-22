---
title: Applications dans les Q# bibliothèques standard
description: 'Découvrez deux applications fondamentales dans quantum computing : la simulation de la formation Hamilton et l’algorithme de recherche de Shori.'
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 115cd65621afd8272887b36163b066a4e6a554d7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835653"
---
# <a name="applications"></a>Applications #

## <a name="hamiltonian-simulation"></a>Simulation hamiltonienne ##

La simulation des systèmes quantiques est l’une des applications les plus passionnantes du calcul Quantum.
Sur un ordinateur classique, la difficulté de simuler le mécanisme quantique, en général, est mise à l’échelle avec la dimension $N $ de sa représentation de vecteur d’État.
Comme cette représentation s’agrandit de façon exponentielle avec le nombre de $n $ qubits $N = 2 ^ n $, une caractéristique connue également sous le nom [de « Curse of Dimensional](xref:microsoft.quantum.concepts.multiple-qubits)», la simulation de Quantum sur le matériel classique est inversée.

Toutefois, la situation peut être très différente sur le matériel Quantum. La variation la plus courante de la simulation de Quantum est appelée problème de simulation de la durée de la simulation indépendante du temps. À partir de là, une description du système Hamilton $H $, qui est une matrice Hermitian, et un État Quantum initial de $ \ket{\Psi (0)} $ qui est encodé sur $n $ qubits sur un ordinateur Quantum, sont fournies. Comme les États quantiques dans les systèmes fermés évoluent sous l’équation Schrödinger $ $ \begin{align} i\frac {d \ket{\Psi (t)}} {d t} & = H \ket{\Psi (t)}, \end{align} $ $ l’objectif est d’implémenter l’opérateur d’évolution de l’heure unitaire $U (t) = e ^ {-iHt} $ à un moment fixe $t $, où $ \ket{\Psi (t)} = U (t) \ket{\Psi (0)} $ résout l’équation Schrödinger.
De même, le problème de simulation de la durée de la simulation, qui dépend du temps, résout la même équation, mais avec $H (t) $ Now.

La simulation de Hamilton est un composant majeur de nombreux autres problèmes de simulation de Quantum, tandis que les solutions à un problème de simulation de la haute---Hamilton sont des algorithmes qui décrivent une séquence de portes quantiques primitives permettant de synthétiser un \tilde{U} d’unités de $ \\ \\ dans la [norme spectrale](xref:microsoft.quantum.concepts.matrix-advanced). La complexité de ces algorithmes dépend fortement de la façon dont une description de l’intérêt de la personne en question est rendue accessible par un ordinateur quantique. Par exemple, dans le pire des cas, si $H $ Status sur $n $ qubits devait être fourni sous la forme d’une liste de $2 ^ n \times 2 ^ n $ Numbers, un pour chaque élément de matrice, il suffit de lire les données pour qu’elles requièrent déjà un temps exponentiel. Dans le meilleur des cas, il peut s’agir d’un accès à une unité de boîte noire qui $O \ket{t}\ket{\Psi (0)} = \ket{t}U (t) \ket{\Psi (0)} $ triflacon résout le problème. Aucun de ces modèles d’entrée n’est particulièrement intéressant : le premier, car il n’est pas mieux que les approches classiques, et ce dernier comme la boîte noire masque la complexité de la porte primitive de son implémentation, qui pourrait être exponentielle dans le nombre de qubits.

### <a name="descriptions-of-hamiltonians"></a>Descriptions des Hamiltonians ###

Des hypothèses supplémentaires concernant le format de l’entrée sont donc requises. Une balance fine doit être comprise entre les modèles d’entrée qui sont suffisamment descriptifs pour englober des Hamiltonians intéressants, tels que ceux pour les systèmes physiques réalistes ou les problèmes de calcul intéressants, et les modèles d’entrée suffisamment restrictifs pour pouvoir être implémentés efficacement sur un ordinateur quantique. Un large éventail de modèles d’entrée non triviales peut être trouvé dans la documentation et il est compris entre Quantum et classique. 

En guise d’exemples de modèles d’entrée quantique, la [simulation de type Hamilton basé sur les échantillons](http://www.nature.com/articles/s41534-017-0013-7) suppose un accès à la boîte noire aux opérations quantiques qui produisent des copies d’une matrice de densité $ \rho $, qui sont considérées comme étant de type Hamilton $H $. Dans le [modèle d’accès](https://arxiv.org/abs/1202.5822) à l’unité, on suppose que le lieu de la Hamilton se décompose en une somme de l’unité $ $ \begin{align} H & = \sum ^ {d-1} \_ {j = 0} a \_ j \hat{U} \_ j, \end{align} $ $ où $a \_ j>$0 sont coefficients et $ \hat{U} \_ j $ sont des unités. Il est ensuite supposé que l’un d’entre eux a accès à la boîte noire à l' $V Oracle d’unités = \sum ^ {d-1} \_ {j = 0} \Ket{j}\bra{j}\otimes \hat{U} \_ j $ qui sélectionne le $ \hat{U} \_ j $ souhaité. et Oracle $A \ket {0} = \sum ^ {d-1} \_ {j = 0} \sqrt{a \_ j/\ Sum ^ {d-1} \_ {k = 0} \alpha \_ j} \ket{j} $ qui créent un État Quantum codant ces coefficients. Dans le cas d’une simulation de la mise à niveau de la base de la [Hamilton](https://arxiv.org/abs/quant-ph/0301023), on suppose que la matrice Hamilton est une matrice éparse avec uniquement $d = \mathcal{O} (\text{polylog} (N)) $ élément non nul dans chaque ligne. En outre, il suppose l’existence de circuits quantiques efficaces qui génèrent l’emplacement de ces éléments non nuls, ainsi que leurs valeurs. La complexité des [algorithmes de simulation](xref:microsoft.quantum.more-information) de la plus grande taille est évaluée en termes de nombre de requêtes à ces cases noires, et la complexité de la porte primitive dépend alors beaucoup de la difficulté à mettre en œuvre ces cases noires.

> [!NOTE]
> La notation Big-O est couramment utilisée pour décrire la complexité de la mise à l’échelle des algorithmes. À partir de deux fonctions réelles $f, g $, l’expression $g (x) = \mathcal{O} (f (x)) $ signifie qu’il existe une constante positive absolue $x \_ 0, c>$0 de sorte que $g (x) \Le c (x) $ pour tous les $x \ge x \_ $0. 

Dans la plupart des applications pratiques à implémenter sur un ordinateur Quantum, ces cases noires doivent être implémentées de manière efficace, c’est-à-dire avec les portes Quantum de $ \mathcal{O} (\text{polylog} (N)) $ Primitives. Un Hamiltonians simulable plus efficace doit avoir une description classique suffisamment éparpillée. Dans l’une de ces formulations, il est supposé que le sous-type de la Hermitian est décomposé en une somme des parties de la $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j.
\end{align} $ $ en outre, il est supposé que chaque partie, un $H de la même-et de \_ j $, est facile à simuler. Cela signifie que le $e unitaire ^ {-1 \_ j t} $ pour chaque fois $t $ peut être implémenté exactement à l’aide de $ \mathcal{O} (1) $ portes quantiques de la primitive. C’est le cas, par exemple, dans le cas particulier où chaque $H \_ j $ est un Pauli local, ce qui signifie qu’il s’agit de produits tenseur des opérateurs de $ \mathcal{O} (1) $ non-Identity Pauli qui agissent sur la fermeture spatiale qubits. Ce modèle est particulièrement applicable aux systèmes physiques avec une interaction limitée et locale, car le nombre de termes est $d = \mathcal{O} (\text{polylog} (N)) $ et peut être clairement écrit, par exemple, décrit de façon classique, en temps polynomial.

> [!TIP]
> Les Hamiltonians qui se décomposent en une somme des parties peuvent être décrites à l’aide de la bibliothèque de représentation du générateur dynamique. Pour plus d’informations, consultez la section relative à la représentation du générateur dynamique dans [structures de données](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Algorithmes de simulation ###

Un algorithme de simulation de Quantum convertit une description donnée d’un sous-sein en une séquence de portes quantiques primitives qui, dans l’ensemble, est une évolution approximative de la durée de ce même point de la même manière.

Dans le cas particulier où la décomposition de la partie Hamilton se décompose en une somme de Hermitian, la décomposition Trotter-Suzuki est un algorithme particulièrement simple et intuitif pour simuler les Hamiltonians qui se décomposent en une somme des composants Hermitian. Par exemple, un intégrateur de première ordre de cette famille est proche de $ $ \begin{align} U (t) & = \left (e ^ {--- \_ 1 0 t/r} e ^ {-1 à 1 t/r} \_ \cdots e ^ {--m \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ | H \_ j \\ | ^ 2 t ^ 2/r), \end{align} $ $ utilisant un produit de $r d $ terms. 

> [!TIP]
> Les applications de l’algorithme de simulation Trotter-Suzuki sont abordées dans les exemples.
> Pour le modèle Ising utilisant uniquement les opérations intrinsèques fournies par chaque ordinateur cible, consultez l' [exemple **SimpleIsing** ](https://github.com/microsoft/Quantum/blob/main/samples/simulation/ising/simple).
> Pour le modèle Ising à l’aide de la structure de contrôle de la bibliothèque Trotter-Suzuki, consultez l' [exemple **IsingTrotter** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/trotter-evolution).
> Pour l’hydrogène moléculaire à l’aide de la structure de contrôle de la bibliothèque Trotter-Suzuki, consultez l’exemple de [ **simulation H2** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line).

Dans de nombreux cas, nous aimerions implémenter l’algorithme de simulation, mais ils ne sont pas intéressés par les détails de son implémentation. Par exemple, l’intégrateur de deuxième ordre se rapproche de $ $ \begin{align} U (t) & = \left (e ^ {-- \_ 1 0 t/2R} e ^ {-1 à 1 t/2R \_ } \cdots e ^ {---u \_ {d-1} t/2R} e ^ {- \_ \cdots {d-1} t/2R} e ^ {- \_ 1-1 t/2R} e ^ {--1 \_ 0 t/2R} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j \\ | H \_ j \\ | ^ 3 t ^ 3/r ^ 2), \end{align} $ $ utilisant un produit de $2rd $ terms. Les commandes plus volumineuses impliquent encore plus de termes et les variantes optimisées peuvent nécessiter des commandes très simples sur les exponentiels. D’autres algorithmes avancés peuvent également impliquer l’utilisation de Ancilla qubits dans les étapes intermédiaires. Nous allons donc empaqueter des algorithmes de simulation dans Canon comme type défini par l’utilisateur

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

Le premier paramètre `Double` est l’heure de la simulation, le deuxième paramètre `EvolutionGenerator` , couvert dans la section relative à la représentation du générateur dynamique des [structures de données](xref:microsoft.quantum.libraries.data-structures), est une description classique d’un lieu de Hamilton indépendant du temps, avec des instructions sur la façon dont chaque terme dans le lieu de la zone Hamilton peut être simulé par un circuit quantique. Les types de ce formulaire se rapprochent de l’opération unitaire $e ^ {-iHt} $ sur le troisième paramètre `Qubit[]` , qui est le Registre qui stocke l’État Quantum du système simulé. De même, pour le cas dépendant du temps, nous définissons un type défini par l’utilisateur avec un type à la `EvolutionSchedule` place, qui est une description classique d’un lieu de type Hamilton dépendant du temps.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Par exemple, la décomposition Trotter-Suzuki peut être appelée à l’aide des fonctions Canon suivantes, avec des paramètres `trotterStepSize` modifiant la durée de la simulation dans chaque exponentiel et `trotterOrder` pour l’ordre de l’intégrateur souhaité.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> Les applications de la bibliothèque de simulation sont abordées dans les exemples. Pour l’estimation de phase dans le modèle Ising à l’aide de `SimulationAlgorithm` , consultez l' [exemple **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation).
> Pour la préparation de l’État adiabatic dans le modèle Ising à l’aide de `TimeDependentSimulationAlgorithm` , consultez l' [exemple **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Estimation de la phase de préparation de l’État adiabatic & ###

Une application courante de la simulation de la Hamilton est la préparation de l’État adiabatic. Ici, un est fourni avec deux Hamiltonians $H \_ {\text{Start}} $ et $H \_ {\text{end}} $, et un État Quantum $ \ket{\Psi (0)} $ qui est un État du sol de la $H start Hamilton \_ {\text{Start}} $. En général, $H \_ {\text{Start}} $ est choisi, de sorte que $ \ket{\Psi (0)} $ est facile à préparer à partir d’un état de base de calcul $ \ket{0\cdots 0} $. En interpolent suffisamment lentement entre ces Hamiltonians dans le problème de simulation dépendant du temps, il est possible de se retrouver, avec une probabilité élevée, dans un État du sol de la version de la version finale de la région de la $H \_ {\text{end}} $. Bien qu’il soit possible de préparer de bonnes approximations aux États de la terre de Hamilton, en appelant sur les algorithmes de simulation de la simulation d’une sous-routine en tant que sous-routine, d’autres approches conceptuelles différentes, telles que les eigensolver quantiques variantes, sont possibles.

Une autre application omniprésente en chimie Quantum consiste à estimer l’énergie de l’état du sol des Hamiltonians représentant les étapes intermédiaires de la réaction chimique. Ce type de schéma pourrait, par exemple, s’appuyer sur la préparation de l’état de adiabatic pour créer l’état du sol, puis incorporer la simulation de la phase de production indépendante du temps en tant que sous-routine dans la caractérisation de l’estimation de la phase pour extraire cette énergie avec une erreur finie et une probabilité de réussite. 

Abstraction des algorithmes de simulation en tant que types définis par l’utilisateur `SimulationAlgorithm` et `TimeDependentSimulationAlgorithm` nous permettre d’intégrer facilement leurs fonctionnalités dans des algorithmes Quantum plus sophistiqués. Cela nous incite à faire de même pour ces sous-routines couramment utilisées.

Nous définissons donc la fonction pratique

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Cela retourne une opération unitaire qui implémente toutes les étapes de préparation de l’État adiabatic. Le premier paramètre `interpolatedTime` définit la durée pendant laquelle nous interpolent de façon linéaire entre le début de la Hamilton, décrit par le deuxième paramètre `evolutionGeneratorStart` et l’end Hamilton décrit par le troisième paramètre `evolutionGeneratorEnd` . Le quatrième paramètre `timeDependentSimulationAlgorithm` est l’endroit où un algorithme de simulation est choisi. Notez que si `interpolatedTime` est suffisamment long, un état initial de la terre reste un état de terre instantané de la région de la même manière sur toute la durée de la simulation dépendante du temps, et se termine donc à l’état du sol de la fin de la Hamilton.

Nous définissons également une opération utile qui effectue automatiquement toutes les étapes d’une expérience de type chimie Quantum typique. Par exemple, nous avons les éléments suivants, qui retournent une estimation d’énergie de l’État produit par la préparation de l’État adiabatic :

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits` nombre de qubits utilisés pour encoder l’État Quantum initial. `statePrepUnitary` prépare l’état de démarrage à partir de la base de calcul $ \ket{0\cdots 0} $. `adiabaticUnitary` est l’opération unitaire qui implémente la préparation de l’État adiabatic, telle que produite par la  `InterpolatedEvolution` fonction. `qpeUnitary` est l’opération unitaire qui est utilisée pour effectuer une estimation de phase sur l’État Quantum résultant. `phaseEstAlgorithm` est notre choix d’algorithme d’estimation de phase.

> [!TIP]
> Les applications de préparation de l’État adiabatic sont traitées dans les exemples. Pour le modèle Ising utilisant une implémentation manuelle de la préparation de l’état de adiabatic et l’utilisation de la `AdiabaticEvolution` fonction, consultez l' [exemple **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/adiabatic).
> Pour l’estimation de phase et la préparation de l’État adiabatic dans le modèle Ising, consultez l' [exemple **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation).

> [!TIP]
> La [simulation de l’hydrogène moléculaire](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) est un exemple intéressant et bref. Le modèle et les résultats expérimentaux ont été signalés dans [O’Malley et. al.](https://arxiv.org/abs/1512.06860) nécessite uniquement des matrices Pauli et prend la forme $ \hat H = g \_ {0} I \_ 0i \_ 1 + g \_ 1 {z \_ 0} + g \_ 2 {Z \_ 1} + g \_ 3 {z 0 \_ } {z \_ 1} + g \_ 4 {y \_ 0} {y 1} \_ + g \_ 5 {x \_ 0} {x \_ 1} $. Il s’agit d’un lieu de Hamilton efficace qui ne requiert que 2 qubits, où les constantes $g $ sont calculées à partir de la distance $R $ entre les deux atomes d’hydrogène. À l’aide des fonctions Canon, les Paulis sont convertis en unités, puis évoluées sur de courtes périodes à l’aide de la décomposition Trotter-Suzuki. Une bonne approximation de l’état du sol $H _2 $ peut être créée sans utiliser la préparation de l’état de la adiabatic, et l’énergie de l’état du sol peut donc être trouvée directement en utilisant l’estimation de phase de l’Canon.

## <a name="shors-algorithm"></a>Algorithme de Shor ##
L’algorithme de Shori reste l’un des développements les plus significatifs de l’informatique Quantum, car il a montré que les ordinateurs quantiques pouvaient être utilisés pour résoudre des problèmes importants, actuellement des problèmes d’inversion classiques.
L’algorithme de Shori offre un moyen rapide de factoriser de grands nombres à l’aide d’un ordinateur quantique, un problème appelé *factorisation*.
La sécurité de nombreux Cryptosystems en cours d’existence est basée sur l’hypothèse qu’il n’existe aucun algorithme rapide pour la factorisation.
Ainsi, l’algorithme de Shori a eu un impact important sur la façon dont nous pensons à la sécurité dans un monde postérieur au quantum.

L’algorithme de Shori peut être considéré comme un algorithme hybride.
L’ordinateur Quantum est utilisé pour effectuer une tâche matérielle de calcul connue sous le nom de période de recherche.
Les résultats de la recherche de période sont ensuite traités de façon classique pour estimer les facteurs.
Nous allons passer en revue ces deux étapes ci-dessous.

### <a name="period-finding"></a>Recherche de période ###

Après avoir vu comment le fonctionnement de la transformation de Fourier quantique et l’estimation de phase (voir [algorithmes Quantum](xref:microsoft.quantum.libraries.standard.algorithms)), nous pouvons utiliser ces outils pour résoudre un problème de calcul classique appelé *période de recherche*.  Dans la section suivante, nous verrons comment appliquer la détection de période à la factorisation.

À partir de deux entiers $a $ et $N $, où $a<N $, l’objectif de la recherche de la période, également appelée recherche de commande, est de trouver la _commande_ $r $ de $a $ modulo $N $, où $r $ est défini comme étant le moins positif $a ^ r \equiv 1 \text{mod} N $.  

Pour trouver la commande à l’aide d’un ordinateur Quantum, nous pouvons utiliser l’algorithme d’estimation de la phase appliqué à l’opérateur d’unités suivant $U _a $ : $ $ U_a \ket{x} \equiv \ket{(ax) \text{mod} N}. $ $ vecteurs propres de $U _a $ sont des nombres entiers $s $ et $0 \ Leq s \leq r-$1, $ $ \ket{x_s} \equiv 1/\sqrt{r} \sum \_ {k = 0} ^ {r-1} e ^ {\frac{-2\pi i SK} {r}} \ket{a ^ k\text {mod} N}, $ $ sont _eigenstates_ de $U _A $.
Le valeurs propres de $U _a $ est $ $ U \_ a \ket{x \_ s} = e ^ {2 \ pi i s/r} \ket{x \_ s}. $$

L’estimation de la phase génère donc la valeurs propres $e ^ {2 \ pi i s/r} $ à partir de laquelle $r $ peut être appris efficacement à l’aide de [fractions continues](https://en.wikipedia.org/wiki/Continued_fraction) de $s/r $.

Le schéma de circuit pour la période Quantum Finding est le suivant :

![Diagramme de circuit pour la recherche d’une période de Quantum](~/media/QPE.svg)

Ici, $2n $ qubits est initialisé à $ \ket {0} $ et $n $ qubits sont initialisés à $ \ket {1} $.
À nouveau, le lecteur peut se demander pourquoi le registre quantique contenant le eigenstates est initialisé à $ \ket {1} $.
Comme il ne sait pas que l’ordre $r $ à l’avance, nous ne pouvons pas préparer les États $ \ket{x_s} $ directement.
Heureusement, il s’avère que $1/\ sqrt {r} \sum \_ {s = 0} ^ {r-1} \ket{x \_ s} = \ket {1} $.
Nous n’avons pas besoin de préparer réellement $ \ket{x} $ !
Nous pouvons simplement préparer un registre quantique de $n $ qubits dans l’État $ \ket {1} $. 

Le circuit contient les QFT et plusieurs portes contrôlées.
La porte QFT a été décrite [précédemment](xref:microsoft.quantum.libraries.standard.algorithms).
Le $U contrôlé _a $ Gate mappe $ \ket{x} $ à $ \ket{(ax) \text{mod} N} $ si le contrôle qubit est $ \ket {1} $, et mappe $ \ket{x} $ à $ \ket{x} $ dans le cas contraire.

Pour obtenir $ (a ^ NX) \text{mod} N $, nous pouvons simplement appliquer le contrôle de $U _ {a ^ n} $, où nous calculons $a ^ n \text{mod} N $ de façon classique pour brancher le circuit Quantum.  
Les circuits permettant d’atteindre ce type d’arithmétique modulaire ont été décrits dans la documentation sur les opérations [arithmétiques Quantum](./algorithms.md#arithmetic), en particulier, nous avons besoin d’un circuit modulaire à élévation à la puissance pour implémenter les opérations de $U de contrôle \_ {a ^ i} $.

Alors que le circuit ci-dessus correspond à l' [estimation de phase quantique](xref:microsoft.quantum.characterization.quantumphaseestimation) et active explicitement la recherche de commande, nous pouvons réduire le nombre de qubits requis. Nous pouvons soit suivre la méthode de Beauregard pour trouver la commande comme décrit [à la page 8 de arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8), soit utiliser l’une des routines d’estimation de phase disponibles dans Microsoft. Quantum. caractérisation. Par exemple, l' [estimation de phase robuste](xref:microsoft.quantum.characterization.robustphaseestimation) utilise également un qubit supplémentaire.
 
### <a name="factoring"></a>Factorisation ###
L’objectif de la factorisation est de déterminer les deux facteurs premiers de l’entier $N $, où $N $ est un nombre $n de $ bits.  
La factorisation se compose des étapes décrites ci-dessous. Les étapes sont divisées en trois parties : une routine de prétraitement classique (1-4); une routine quantum computing pour trouver l’ordre de $a \text{mod} N $ (5); et une routine de post-traitement classique pour dériver les facteurs premiers de la commande (6-9).

La routine de prétraitement classique comprend les étapes suivantes :
1. Si $N $ est pair, retournez le facteur premier $2 $.
2. Si $N = p ^ q $ pour $p \geq1 $, $q \geq2 $, retourne le facteur principal $p $.  Cette étape est effectuée de façon classique.
3. Choisissez un nombre aléatoire $a $ de sorte que $1 < a < N-$1.
4. Si $ \text{GCD} (a, N) >$1, retourner le facteur de prime $ \text{GCD} (a, N) $. Cette étape est calculée à l’aide de l’algorithme de Euclide permettant.
Si aucun facteur principal n’a été retourné, nous procédons à la routine Quantum :
5. Appelez l’algorithme de recherche de période de Quantum pour calculer la commande $r $ sur $a \text{mod} N $. Utilisez $r $ dans la routine de post-traitement classique pour déterminer les facteurs premiers :
6. Si $r $ est impair, revenez à l’étape de prétraitement (3).
7. Si $r $ est pair et $a ^ {r/2} =-1 \ Text {mod} N $, revenez à l’étape de prétraitement (3).
8. Si $ \text{GCD} (a ^ {r/2} + 1, N) $ est un facteur non négligeable de $N $, retournez $ \text{GCD} (a ^ {r/2} + 1, N) $.
9. Si $ \text{GCD} (a ^ {r/2}-1, N) $ est un facteur non négligeable de $N $, retournez $ \text{GCD} (a ^ {r/2}-1, N) $.


L’algorithme de factorisation est probabiliste : il peut être démontré qu’avec une probabilité d’au moins une demi-$r $ sera même et $a ^ {r/2} \neq-1 \text{mod} N $, produisant ainsi un facteur premier.  (Pour plus d’informations, consultez le [document original de Shori](https://doi.org/10.1109/SFCS.1994.365700) ou l’un des textes de *base de quantum computing* dans [pour plus d’informations](xref:microsoft.quantum.more-information)).
Si un facteur principal n’est pas retourné, il suffit de répéter l’algorithme à partir de l’étape (1).  Une fois que $n $ tentatives, la probabilité que chaque tentative ait échoué est au maximum de $2 ^ {-n} $.
Ainsi, après la répétition de l’algorithme, un petit nombre de fois où la réussite est pratiquement assurée.
