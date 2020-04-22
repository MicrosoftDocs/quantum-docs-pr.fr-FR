---
title: Glossaire de calcul quantique
description: Un glossaire de termes, actions et objets communs utilisés dans l’informatique quantique.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482236"
---
# <a name="quantum-computing-glossary"></a>Glossaire de calcul quantique

## <a name="adjoint"></a>Adjoint

La transpose conjugale complexe d’une [opération](xref:microsoft.quantum.glossary#operation). Pour les opérations qui mettent en œuvre un opérateur [unitaire,](xref:microsoft.quantum.glossary#unitary-operator) l’adjoint est l’inverse de l’opération et est indiqué par un symbole de poignard. Par exemple, si `U` l’opération représente l’opérateur unitaire $U$, cela `Adjoint U` représente $U$dagger$. Pour plus d’informations, voir [Adjoint](xref:microsoft.quantum.language.file-structure#adjoint).

## <a name="ancilla"></a>Ancilla

Un [qubit](xref:microsoft.quantum.glossary#qubit) qui sert de mémoire temporaire pour un ordinateur quantique et est alloué et dé-alloué au besoin.  Pour plus d’informations, voir [plusieurs qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>État de Bell

Un des quatre [états quantiques](xref:microsoft.quantum.glossary#quantum-state) [enchevêtrés](xref:microsoft.quantum.glossary#entanglement) au maximum spécifiques de deux qubits. Les quatre états sont définis à 1 000 euros et à beta_ 'ij' ("mathbb’I" 'otimes X’iZ’j) (ket{00} 'ket{11}'' / 'sqrt$.{2} Un état Bell est également connu comme une [paire EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Sphère Bloch

Une représentation graphique d’un[qubit](xref:microsoft.quantum.glossary#qubit) [état quantique](xref:microsoft.quantum.glossary#quantum-state) unique en tant que point dans une sphère unitaire tridimensionnelle. Pour plus d’informations, voir [Visualizing Qubits and Transformations à l’aide de la sphère Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Callable

Une [opération](xref:microsoft.quantum.glossary#operation) ou [une fonction](xref:microsoft.quantum.glossary#function) dans la langue Q. Pour plus d’informations, consultez [les types d’opération et de fonction](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="clifford-group"></a>Groupe Clifford

L’ensemble des opérations qui occupent les octants de la [sphère Bloch](xref:microsoft.quantum.glossary#bloch-sphere) et les permutations d’effet des [opérateurs Pauli](xref:microsoft.quantum.glossary#pauli-operators). Il s’agit notamment des opérations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) et [$S$](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Contrôlé

Une [opération](xref:microsoft.quantum.glossary#operation) quantique qui prend un ou plusieurs [qubits](xref:microsoft.quantum.glossary#qubit) comme facilitateurs pour l’opération cible. Pour plus d’informations, voir [Contrôle](xref:microsoft.quantum.language.type-model#controlled).

## <a name="dirac-notation"></a>Dirac Notation

Un raccourci symbolique qui simplifie la représentation des [états quantiques,](xref:microsoft.quantum.glossary#quantum-state)également appelé notation *de soutien-gorge-ket.*  La portion *de soutien-gorge* représente un vecteur de ligne, par exemple , «bret à-bmatrix» A '1' & A '2 ' 'end 'bmatrix'$ et la partie *de ket* représente un \\ \\ vecteur de colonne, $'ket 'B' '''bmatrix’B 'B 'B 'B 'B 'B 'B 'B '2 'end b '. Pour plus d’informations, voir [Dirac Notation](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

Le facteur par lequel l’ampleur d’un [eigenvector](xref:microsoft.quantum.glossary#eigenvector) d’une transformation donnée est modifié par l’application de la transformation.  Compte tenu d’une matrice carrée $M$ et un eigenvector $v$, puis $Mv cv$, où $c$ est l’eigenvalue et peut être un nombre complexe de tout argument. Pour plus d’informations, voir [Concepts de matrice avancée](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

Un vecteur dont la direction est inchangée par une transformation donnée et dont l’ampleur est modifiée par un facteur correspondant à [l’eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)de ce vecteur. Compte tenu d’une matrice carrée $M$ et une eigenvalue $c$, puis $Mv - cv$, où $v$ est un eigenvector de la matrice et peut être un nombre complexe de tout argument. Pour plus d’informations, voir [Concepts de matrice avancée](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Enchevêtrement

Les particules quantiques, telles que [les qubits,](xref:microsoft.quantum.glossary#qubit)peuvent être connectées ou *enchevêtrées* de telle sorte qu’elles ne peuvent pas être décrites indépendamment les unes des autres. Leurs résultats de mesure sont corrélés même lorsqu’ils sont séparés infiniment loin. L’enchevêtrement est essentiel pour [mesurer](xref:microsoft.quantum.glossary#measurement) [l’état](xref:microsoft.quantum.glossary#quantum-state) d’un qubit.  Pour plus d’informations, voir [Concepts de matrice avancée](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>Paire EPR

Un des quatre états [quantiques](xref:microsoft.quantum.glossary#quantum-state) enchevêtrés au maximum spécifiques de deux [qubits](xref:microsoft.quantum.glossary#qubit). Les quatre états sont définis à 1 000 $ beta_{1} 'ij' (mathbb 'otimes X’iZ’j) (ket{00} 'ket{11}'' / 'sqrt{2}$. Une paire EPR est également connue sous le nom [d’état Bell](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Évolution

Comment un [état quantique](xref:microsoft.quantum.glossary#quantum-state) change avec le temps. Pour plus d’informations, voir [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Fonction
Un type de sous-route dans la langue Q qui est purement classique (non quantique). Bien que les fonctions soient utilisées dans les algorithmes quantiques, elles ne peuvent pas agir sur [les qubits](xref:microsoft.quantum.glossary#qubit) ou [les opérations](xref:microsoft.quantum.glossary#operation)d’appel. Pour plus d’informations, consultez [les types d’opération et de fonction](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="gate"></a>Porte

Un terme hérité pour une [opération](xref:microsoft.quantum.glossary#operation)quantique, basé sur le concept de portes logiques classiques. Un [circuit quantique](xref:microsoft.quantum.glossary#quantum-circuit-diagram) est un réseau de portes (ou d’opérations), basé sur le concept similaire de circuits logiques classiques.

## <a name="global-phase"></a>Phase globale

Lorsque deux [États](xref:microsoft.quantum.glossary#quantum-state) sont identiques jusqu’à un multiple d’un nombre complexe $e-i-phi,phi,« ils sont dits différer jusqu’à une phase globale. Contrairement aux phases locales, les phases globales ne peuvent être observées par aucune [mesure](xref:microsoft.quantum.glossary#measurement). Pour plus d’informations, voir [The Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

L’opération Hadamard (également appelée porte Hadamard ou transformation) agit sur un seul [qubit](xref:microsoft.quantum.glossary#qubit) et le{0}met dans une{1} [superposition](xref:microsoft.quantum.glossary#superposition) égale de $ket ${0}ou $ket $ si le qubit est initialement dans l’état de $ket $. Dans le Q, cette opération est [`H`](xref:microsoft.quantum.intrinsic.h) appliquée par l’opération prédéfinise.

## <a name="immutable"></a>Non modifiable

Une variable dont la valeur ne peut être modifiée. Une variable immuable dans Q `let` est créée à l’aide du mot clé. Pour déclarer les variables qui *peuvent* être [modifiées,](xref:microsoft.quantum.glossary#immutable) utilisez le mot clé mutable à déclarer et le `set` mot clé pour modifier la valeur. 

## <a name="measurement"></a>Mesure

Une manipulation d’un [qubit](xref:microsoft.quantum.glossary#qubit) (ou un ensemble de qubits) qui donne le résultat d’une observation, en effet l’obtention d’un bit classique. Pour plus d’informations, voir [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Mutable

Une variable dont la valeur peut être modifiée après sa création. Une variable mutable dans Q `mutable` est déclarée `set` à l’aide du mot clé et modifiée à l’aide du mot clé. Les variables `let` créées avec le mot clé sont [immuables](xref:microsoft.quantum.glossary#immutable) et leur valeur ne peut pas être modifiée.

## <a name="namespace"></a>Espace de noms

Une étiquette pour une collection de noms connexes (c.-à-d. [opérations,](xref:microsoft.quantum.glossary#operation) [fonctions](xref:microsoft.quantum.glossary#function)et [types définis par l’utilisateur).](xref:microsoft.quantum.glossary#user-defined-type) Par exemple, l’espace nom [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) étiquettes tous les symboles définis dans la bibliothèque standard qui aident à préparer les états initiaux.

## <a name="operation"></a>Opération

L’unité de base de l’exécution quantique dans le Q. Il est à peu près équivalent à une fonction en C, CM ou Python, ou une méthode statique en C ou Java. Pour plus d’informations, consultez [les types d’opération et de fonction](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="operator-application"></a>Application de l’opérateur

Effectuer une opération quantique. Cela applique généralement une matrice unitaire au vecteur actuel de l’état quantique.

## <a name="oracle"></a>Oracle

Une sous-route qui fournit des informations dépendantes des données à un algorithme quantique au moment de l’exécution. Typiquement, l’objectif est de fournir une [superposition](xref:microsoft.quantum.glossary#superposition) de sorties correspondant aux entrées qui sont en superposition. Pour plus d’informations, voir [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Application partielle

Appel d’une [fonction](xref:microsoft.quantum.glossary#function) ou [d’une opération](xref:microsoft.quantum.glossary#operation) sans toutes les entrées requises. Cela renvoie un nouvel [appel qui](xref:microsoft.quantum.glossary#callable) n’a besoin que des paramètres manquants (indiqués par un soulignement) à fournir lors d’une future application. Par exemple, étant `MyFunc(x : int, y : int) : int {return x + y;}` donné la fonction, vous `let NewFunc = MyFunc(_, 3)`pouvez l’appliquer partiellement à une nouvelle fonction . Vous pouvez ensuite appeler la nouvelle fonction à `NewFunc(2)` une date ultérieure avec le paramètre manquant qui renvoie la valeur *5*.  Pour plus d’informations, voir [application Partielle](xref:microsoft.quantum.language.expressions#partial-application).

## <a name="pauli-operators"></a>Opérateurs Pauli

Un ensemble de trois 2 x 2 matrices unitaires connues sous le nom de , `X` `Y` et `Z` les opérations quantiques. La matrice d’identité, $I$, est souvent incluse dans l’ensemble ainsi.  $I 'begin’bmatrix' 1 \\ \\ & 0 0 & 1 'end’bmatrix'$, $X 'begin’bmatrix' 0 & 1 \\ \\ 1 & 0 'end’bmatrix'$, $Y 'begin’bmatrix' 0 & -i \\ \\ i & 0 'end’bmatrix'$, $Z 'begin’bmatrix' 1 & 0 \\ \\ & -1 'end’bmatrix'$.   Pour plus d’informations, voir [opérations à simple qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagramme de circuit quantique

Une méthode pour représenter graphiquement la séquence des [opérations](xref:microsoft.quantum.glossary#operation) (ou ![des](~/media/qpe.png) [portes](xref:microsoft.quantum.glossary#gate)) pour des programmes quantiques simples, par exemple Diagramme de circuit d’échantillon . Pour plus d’informations, voir [circuits Quantum](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Bibliothèques quantiques

Collections [d’opérations,](xref:microsoft.quantum.glossary#operation) [fonctions](xref:microsoft.quantum.glossary#function) et types [définis par l’utilisateur](xref:microsoft.quantum.glossary#user-defined-type) pour la création de programmes Q. La [bibliothèque Standard](xref:microsoft.quantum.libraries.standard.intro) est installée par défaut. D’autres bibliothèques sont disponibles sont la [bibliothèque de chimie](xref:microsoft.quantum.chemistry.concepts.intro), la bibliothèque [Numerics](xref:microsoft.quantum.numerics.intro) et la [bibliothèque d’apprentissage Machine](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>État quantique

L’état précis d’un système quantique isolé, à partir duquel les probabilités de [mesure](xref:microsoft.quantum.glossary#measurement) peuvent être extraites. Dans l’informatique quantique, le simulateur quantique utilise ces informations pour simuler la façon dont les qubits réagissent aux opérations. Pour plus d’informations, voir [The Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Une unité de base de l’information quantique, analogue à un *peu* dans l’informatique classique. Pour plus d’informations, voir [The Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Répéter jusqu’au succès

Un algorithme quantique qui réussit probabilistiquement. Lors de l’échec, la routine sera réessayer jusqu’à ce que le succès (ou une limite a été atteint). Pour plus d’informations, voir [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>Bibliothèques standard

[Opérations,](xref:microsoft.quantum.glossary#operation) [fonctions](xref:microsoft.quantum.glossary#function) et [types définis par l’utilisateur](xref:microsoft.quantum.glossary#user-defined-type) qui sont installés avec le compilateur Qmd pendant l’installation. La mise en œuvre standard de la bibliothèque est agnostique en ce qui concerne les machines cibles. Pour plus d’informations, voir [bibliothèques Standard](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Superposition

Le concept dans l’informatique quantique qu’un [qubit](xref:microsoft.quantum.glossary#qubit) est une combinaison linéaire de deux états, $ket '0 '$ et $'ket '1 '$, jusqu’à ce qu’il soit [mesuré](xref:microsoft.quantum.glossary#measurement).  Pour plus d’informations, voir [Qu’est-ce que l’informatique quantique](xref:microsoft.quantum.overview.what).

## <a name="target-machine"></a>Machine cible

Une cible de compilation qui abaisse un programme quantique abstrait vers le matériel ou la simulation. Cela inclut généralement des réécritis à de nombreuses fins, y compris le remplacement de la porte, l’encodage pour la correction d’erreur, la disposition géométrique et d’autres. Pour plus d’informations, voir [simulateurs Quantum et applications d’accueil](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Téléportation

Une méthode pour régénérer les données, ou [l’état quantique,](xref:microsoft.quantum.glossary#quantum-state)d’un [qubit](xref:microsoft.quantum.glossary#qubit) d’un endroit à l’autre sans déplacer physiquement le qubit, en utilisant [l’enchevêtrement](xref:microsoft.quantum.glossary#entanglement) et [la mesure](xref:microsoft.quantum.glossary#measurement).  Pour plus d’informations, voir [les circuits Quantum](xref:microsoft.quantum.concepts.circuits) et mettre tout cela [ensemble](xref:microsoft.quantum.techniques.puttingittogether).

## <a name="tuple"></a>Tuple

Une collection de valeurs séparées par virgule qui agit comme une valeur unique. Le *type* de tuple est défini par les types de valeurs qu’il contient. Dans le Q, les tuples sont [immuables](xref:microsoft.quantum.glossary#immutable) et peuvent être immuables, contenir des tableaux ou être utilisés dans un tableau. Pour plus d’informations, voir [types Tuple](xref:microsoft.quantum.language.type-model#tuple-types).

## <a name="unitary-operator"></a>Opérateur unitaire

Un opérateur dont l’inverse est égal à son [adjoint,](xref:microsoft.quantum.glossary#adjoint)c’est-à-dire $UU 'dagger'.

## <a name="user-defined-type"></a>Type défini par l'utilisateur

Une collection de types intégrés ou définis antérieurement qui peuvent être désignés comme une seule unité. Pour plus d’informations, voir [les types définis par l’utilisateur](xref:microsoft.quantum.language.type-model#user-defined-types).