---
title: Glossaire quantum computing
description: Glossaire des termes, actions et objets les plus courants utilisés dans quantum computing.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: cbc473eb14d8afd255a7072475dc054e18b98e3e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426700"
---
# <a name="quantum-computing-glossary"></a>Glossaire quantum computing

## <a name="adjoint"></a>Voisin

Transpose complexe conjugué d’une [opération](xref:microsoft.quantum.glossary#operation). Pour les opérations qui implémentent un opérateur unitaire, l' [entité](xref:microsoft.quantum.glossary#unitary-operator) voisine est l’inverse de l’opération et est indiquée par un symbole poignard. Par exemple, si l’opération `U` représente l’opérateur d’unité $U $, `Adjoint U` représente $U ^ \dagger $. Pour plus d’informations, consultez [joint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="ancilla"></a>Ancilla

Un [qubit](xref:microsoft.quantum.glossary#qubit) qui sert de mémoire temporaire pour un ordinateur quantique et qui est alloué et désalloué en fonction des besoins.  Pour plus d’informations, consultez [plusieurs qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>État de la cloche

L’un des quatre [entangled](xref:microsoft.quantum.glossary#entanglement) [États quantiques](xref:microsoft.quantum.glossary#quantum-state) des deux qubits. Les quatre États sont définis : $ \ket{\ beta_ {IJ}} = (\mathbb{I} \otimes X ^ iZ ^ j) (\ket {00} + \ket {11} )/\sqrt {2} $. Un état de cloche est également appelé [paire de EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Sphère Bloch

Représentation graphique d’un [État Quantum](xref:microsoft.quantum.glossary#quantum-state) à[qubit](xref:microsoft.quantum.glossary#qubit) unique comme point dans une sphère d’unité en trois dimensions. Pour plus d’informations, consultez [visualisation des qubits et des transformations à l’aide de la sphère Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Pouvant être appelé

Une [opération](xref:microsoft.quantum.glossary#operation) ou une [fonction](xref:microsoft.quantum.glossary#function) dans le langage Q #. Pour plus d’informations, consultez [opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="clifford-group"></a>Groupe Clifford

L’ensemble des opérations qui occupent le octants de la [sphère Bloch](xref:microsoft.quantum.glossary#bloch-sphere) et les permutations d’effet des [opérateurs Pauli](xref:microsoft.quantum.glossary#pauli-operators). Celles-ci incluent les opérations [$X $](xref:microsoft.quantum.intrinsic.x), [$Y $](xref:microsoft.quantum.intrinsic.y), [$Z $](xref:microsoft.quantum.intrinsic.z), [$H $](xref:microsoft.quantum.intrinsic.h) et [$S $](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Contrôl

[Opération](xref:microsoft.quantum.glossary#operation) de Quantum qui prend un ou plusieurs [qubits](xref:microsoft.quantum.glossary#qubit) comme activateurs pour l’opération cible. Pour plus d’informations, consultez [opérations contrôlées et apjointes](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="dirac-notation"></a>Notation Dirac

Raccourci symbolique qui simplifie la représentation des [États quantiques](xref:microsoft.quantum.glossary#quantum-state), également appelée notation *Bra-Ket* .  La partie *Bra* représente un vecteur de ligne, par exemple $ \bra{A} = \begin{bmatrix} a {_ 1} & un {_2} \end{bmatrix} $ et la partie *Ket* représente un vecteur de colonne, $ \ket{B} = \begin{bmatrix} b {_ 1} \\ \\ b {_2} \end{bmatrix} $. Pour plus d’informations, consultez [notation Dirac](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

Facteur par lequel la grandeur d’un [extraction](xref:microsoft.quantum.glossary#eigenvector) d’une transformation donnée est modifiée par l’application de la transformation.  À partir d’une matrice carrée $M $ et d’un extraction $v $, alors $Mv = CV $, où $c $ est le eigenvalue et peut être un nombre complexe d’un argument. Pour plus d’informations, consultez [concepts avancés](xref:microsoft.quantum.concepts.matrix-advanced)de la matrice.

## <a name="eigenvector"></a>Extraction

Vecteur dont la direction est inchangée par une transformation donnée et dont l’amplitude est modifiée par un facteur correspondant au [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)de ce vecteur. À partir d’une matrice carrée $M $ et d’un eigenvalue $c $, alors $Mv = CV $, où $v $ est un extraction de la matrice et peut être un nombre complexe d’un argument. Pour plus d’informations, consultez [concepts avancés](xref:microsoft.quantum.concepts.matrix-advanced)de la matrice.

## <a name="entanglement"></a>Enchevêtrement ni

Les particules quantiques, telles que [qubits](xref:microsoft.quantum.glossary#qubit), peuvent être connectées ou *enchevêtrées* de sorte qu’elles ne puissent pas être décrites indépendamment les unes des autres. Leurs résultats de mesure sont corrélés même lorsqu’ils sont séparés à l’infini. L’enchevêtrement est essentiel à la [mesure](xref:microsoft.quantum.glossary#measurement) de l' [État](xref:microsoft.quantum.glossary#quantum-state) d’un qubit.  Pour plus d’informations, consultez [concepts avancés](xref:microsoft.quantum.concepts.matrix-advanced)de la matrice.

## <a name="epr-pair"></a>Paire EPR

L’un des quatre [États quantiques](xref:microsoft.quantum.glossary#quantum-state) des deux [qubits](xref:microsoft.quantum.glossary#qubit). Les quatre États sont définis : $ \ket{\ beta_ {IJ}} = (\mathbb {1} \Otimes X ^ iz ^ j) (\ket {00} + \ket {11} )/\sqrt {2} $. Une paire EPR est également appelée « [État Bell](xref:microsoft.quantum.glossary#bell-state) ».

## <a name="evolution"></a>Révolution

Comment un [État Quantum](xref:microsoft.quantum.glossary#quantum-state) change dans le temps. Pour plus d’informations, consultez [exponentielles](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)de la matrice.

## <a name="function"></a>Fonction
Type de sous-routine dans le langage Q # qui est purement classique (non Quantum). Tandis que les fonctions sont utilisées dans les algorithmes Quantum, elles ne peuvent pas agir sur les [opérations](xref:microsoft.quantum.glossary#operation)de [qubits](xref:microsoft.quantum.glossary#qubit) ou d’appel. Pour plus d’informations, consultez [opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="gate"></a>Transistor

Terme hérité pour une [opération](xref:microsoft.quantum.glossary#operation)de Quantum, basé sur le concept de portes logiques classiques. Un [circuit Quantum](xref:microsoft.quantum.glossary#quantum-circuit-diagram) est un réseau de portes (ou d’opérations), basé sur le concept similaire des circuits logiques classiques.

## <a name="global-phase"></a>Phase globale

Lorsque deux [États](xref:microsoft.quantum.glossary#quantum-state) sont identiques à un multiple d’un nombre complexe $e ^ {i\phi} $, ils sont considérés comme différents d’une phase globale. Contrairement aux phases locales, les phases globales ne peuvent pas être observées par des [mesurages](xref:microsoft.quantum.glossary#measurement). Pour plus d’informations, consultez [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

L’opération Hadarmard (également appelée porte ou transformation Hadarmard) agit sur un seul [qubit](xref:microsoft.quantum.glossary#qubit) et la place dans une [superposition](xref:microsoft.quantum.glossary#superposition) de $ \ket {0} $ ou de $ \ket {1} $ si le qubit est initialement dans l’État $ \ket {0} $. Dans Q #, cette opération est appliquée par l’opération prédéfinie [`H`](xref:microsoft.quantum.intrinsic.h) .

## <a name="immutable"></a>Non modifiable

Variable dont la valeur ne peut pas être modifiée. Une variable immuable dans Q # est créée à l’aide du `let` mot clé. Pour déclarer des variables qui *peuvent* être modifiées, utilisez le mot clé [mutable](xref:microsoft.quantum.glossary#immutable) pour déclarer et le `set` mot clé pour modifier la valeur. 

## <a name="measurement"></a>Mesure

Manipulation d’un [qubit](xref:microsoft.quantum.glossary#qubit) (ou d’un ensemble de qubits) qui produit le résultat d’une observation, en obtenant un bit classique. Pour plus d’informations, consultez [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Mutable

Variable dont la valeur peut être modifiée après sa création. Une variable mutable dans Q # est déclarée à l’aide du `mutable` mot clé et modifiée à l’aide du `set` mot clé. Les variables créées avec le `let` mot clé sont [immuables](xref:microsoft.quantum.glossary#immutable) et leur valeur ne peut pas être modifiée.

## <a name="namespace"></a>Espace de noms

Étiquette pour une collection de noms associés (c’est-à-dire des [opérations](xref:microsoft.quantum.glossary#operation), des [fonctions](xref:microsoft.quantum.glossary#function)et des [types définis par l’utilisateur](xref:microsoft.quantum.glossary#user-defined-type)). Par exemple, l’espace de noms [Microsoft. Quantum. PREPARATION](xref:microsoft.quantum.preparation) étiquette tous les symboles définis dans la bibliothèque standard qui facilitent la préparation des États initiaux.

## <a name="operation"></a>Opération

Unité de base de l’exécution du quantum dans Q #. Elle est à peu près équivalente à une fonction en C, C++ ou python, ou une méthode statique en C# ou en Java. Pour plus d’informations, consultez [opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="operator-application"></a>Application opérateur

Exécution d’une opération de Quantum. Cela applique généralement une matrice d’unités au vecteur d’État Quantum actuel.

## <a name="oracle"></a>Oracle

Sous-routine qui fournit des informations dépendantes aux données à un algorithme Quantum au moment de l’exécution. En règle générale, l’objectif est de fournir une [superposition](xref:microsoft.quantum.glossary#superposition) des sorties correspondant aux entrées en superposition. Pour plus d’informations, consultez [Oracle](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Application partielle

Appel d’une [fonction](xref:microsoft.quantum.glossary#function) ou d’une [opération](xref:microsoft.quantum.glossary#operation) sans toutes les entrées requises. Cela retourne un nouvel [appelable](xref:microsoft.quantum.glossary#callable) qui n’a besoin que des paramètres manquants (indiqués par un trait de soulignement) à fournir au cours d’une prochaine application. Par exemple, étant donné la fonction, `MyFunc(x : int, y : int) : int {return x + y;}` vous pouvez l’appliquer partiellement à une nouvelle fonction `let NewFunc = MyFunc(_, 3)` . Vous pouvez ensuite appeler la nouvelle fonction ultérieurement avec le paramètre manquant `NewFunc(2)` qui retourne la valeur *5*.  Pour plus d’informations, consultez [application partielle](xref:microsoft.quantum.guide.operationsfunctions#partial-application).

## <a name="pauli-operators"></a>Pauli, opérateurs

Ensemble de trois matrices d’unités de 2 x 2, appelées `X` `Y` opérations de `Z` Quantum et. La matrice d’identité, $I $, est souvent incluse dans le jeu également.  $I = \begin{bmatrix} 1 & 0 \\ \\ 0 & 1 \end{bmatrix} $, $X = \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{bmatrix} $, $Y = \begin{bmatrix} 0 &-i & \\ \\ 0 \end{bmatrix} $, $Z = \begin{bmatrix} 1 & 0 \\ \\ 0 &-1 \end{bmatrix} $.   Pour plus d’informations, consultez [opérations à qubit unique](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagramme de circuit quantique

Méthode pour représenter graphiquement la séquence d' [opérations](xref:microsoft.quantum.glossary#operation) (ou de [portes](xref:microsoft.quantum.glossary#gate)) pour les programmes Quantum simples, par exemple un ![ diagramme de circuit exemple ](~/media/qpe.png) . Pour plus d’informations, consultez la page [circuits quantiques](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Bibliothèques Quantum

Collections d' [opérations](xref:microsoft.quantum.glossary#operation), de [fonctions](xref:microsoft.quantum.glossary#function) et de [types définis](xref:microsoft.quantum.glossary#user-defined-type) par l’utilisateur pour la création de programmes Q #. La [bibliothèque standard](xref:microsoft.quantum.libraries.standard.intro) est installée par défaut. Les autres bibliothèques disponibles sont la [bibliothèque chimie](xref:microsoft.quantum.chemistry.concepts.intro), la [bibliothèque de valeurs numériques](xref:microsoft.quantum.numerics.intro) et la [bibliothèque machine learning](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>État Quantum

État précis d’un système quantique isolé, à partir duquel les probabilités de [mesure](xref:microsoft.quantum.glossary#measurement) peuvent être extraites. Dans Quantum Computing, le simulateur quantum utilise ces informations pour simuler la manière dont qubits répond aux opérations. Pour plus d’informations, consultez [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Unité de base d’informations de Quantum, analogue à un *peu* dans l’informatique classique. Pour plus d’informations, consultez [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Répéter jusqu’à réussite

Un algorithme Quantum qui fonctionne de façon probabiliste. En cas d’échec, la routine réessaie jusqu’à ce qu’elle réussisse (ou qu’une limite a été atteinte). Pour plus d’informations, consultez [répéter jusqu’à la réussite (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>Bibliothèques standard

[Opérations](xref:microsoft.quantum.glossary#operation), [fonctions](xref:microsoft.quantum.glossary#function) et [types définis](xref:microsoft.quantum.glossary#user-defined-type) par l’utilisateur installés avec le compilateur Q # pendant l’installation. L’implémentation de la bibliothèque standard est indépendante en ce qui concerne les ordinateurs cibles. Pour plus d’informations, consultez [bibliothèques standard](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Superposition

Le concept dans quantum computing qu’un [qubit](xref:microsoft.quantum.glossary#qubit) est une combinaison linéaire de deux États, $ \ket{\0} $ et $ \ket{\1} $, jusqu’à ce qu’il soit [mesuré](xref:microsoft.quantum.glossary#measurement).  Pour plus d’informations, consultez [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Ordinateur cible

Cible de compilation qui réduit un programme Quantum abstrait en vue d’un matériel ou d’une simulation. Cela inclut généralement les réécritions pour de nombreuses raisons, notamment le remplacement de la porte, l’encodage pour la correction des erreurs, la disposition géométrique et autres. Pour plus d’informations, consultez [simulations de Quantum et applications hôtes](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Téléportation

Méthode pour régénérer des données, ou l' [État Quantum](xref:microsoft.quantum.glossary#quantum-state), d’un [qubit](xref:microsoft.quantum.glossary#qubit) d’un emplacement à un autre sans déplacer physiquement le qubit, à l’aide d’un [enchevêtrement](xref:microsoft.quantum.glossary#entanglement) et d’une [mesure](xref:microsoft.quantum.glossary#measurement).  Pour plus d’informations, consultez les [circuits quantiques](xref:microsoft.quantum.concepts.circuits) et les Kata respectifs dans [Quantum katas](xref:microsoft.quantum.overview.katas).

## <a name="tuple"></a>Tuple

Collection de valeurs séparées par des virgules qui agit comme une valeur unique. Le *type* d’un tuple est défini par les types de valeurs qu’il contient. Dans Q #, les tuples sont [immuables](xref:microsoft.quantum.glossary#immutable) et peuvent être imbriqués, contenir des tableaux ou utilisés dans un tableau. Pour plus d’informations, consultez [types de tuples](xref:microsoft.quantum.guide.types#tuple-types).

## <a name="unitary-operator"></a>Opérateur unitaire

Opérateur dont l’inverse est égal à son [voisin](xref:microsoft.quantum.glossary#adjoint), c.-à-d. $uu ^ {\dagger} = \ID $.

## <a name="user-defined-type"></a>Type défini par l'utilisateur

Collection de types intégrés ou définis précédemment qui peuvent être référencés comme une seule unité. Pour plus d’informations, consultez [types définis par l’utilisateur](xref:microsoft.quantum.guide.types#user-defined-types).