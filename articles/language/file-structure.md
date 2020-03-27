---
title: 'Structure de fichiers Q #'
description: 'Découvrez comment structurer les espaces de noms, ainsi que les déclarations d’opérations, de fonctions et de types définis par l’utilisateur dans les programmes et les bibliothèques Q #.'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 96de062bc6ce4edf94520bec449e8d95259c0f5c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320771"
---
# <a name="file-structure"></a>Structure de fichiers

Un fichier Q # est constitué d’une séquence de déclarations d’espaces de noms.
Chaque déclaration d’espace de noms contient des déclarations pour les types, les opérations et les fonctions définis par l’utilisateur.
Une déclaration d’espace de noms peut contenir un nombre quelconque de chaque type de déclaration, et dans n’importe quel ordre.
Le seul texte qui peut apparaître en dehors d’une déclaration d’espace de noms est un commentaire.
En particulier, les commentaires de documentation pour un espace de noms précèdent la déclaration.

## <a name="namespace-declarations"></a>Déclarations d'espace de noms

Un fichier Q # dispose généralement d’une seule déclaration d’espace de noms, mais il peut avoir la valeur None (et être vide ou contenir simplement des commentaires) ou peut contenir plusieurs espaces de noms.
Les déclarations d’espaces de noms ne peuvent pas être imbriquées.

Le même espace de noms peut être déclaré dans plusieurs fichiers Q # qui sont compilés ensemble, à condition qu’il n’y ait pas de déclaration de type, d’opération ou de fonction portant le même nom.
En particulier, il n’est pas valide de définir le même type dans le même espace de noms dans plusieurs fichiers, même si les déclarations sont identiques.

Une déclaration d’espace de noms se compose du mot clé `namespace`, suivi du nom de l’espace de noms, d’une accolade ouvrante `{`, des déclarations contenues dans l’espace de noms et d’une accolade fermante `}`.
Les noms d’espaces de noms suivent le modèle .NET d’une séquence d’un ou de plusieurs symboles légaux séparés par des points `.`.
Par exemple, `MyQuantumStuff` et `Microsoft.Quantum.Canon` sont des noms d’espaces de noms valides.
Par Convention, les symboles d’un nom d’espace de noms sont écrits en majuscules, mais cela n’est pas obligatoire.

Les déclarations peuvent apparaître dans n’importe quel ordre dans une déclaration d’espace de noms.
Les références à des types ou des callables déclarés plus loin dans un fichier sont correctement résolues ; Il n’est pas nécessaire que le type, l’opération ou la déclaration de fonction précède une référence à celui-ci.

## <a name="open-directives"></a>Directives Open

Dans un bloc d’espace de noms, la directive `open` peut être utilisée pour importer tous les types et callables définis dans un espace de noms donné et y faire référence par leur nom non qualifié. 

Une telle directive de `open` se compose du mot clé `open`, suivi de l’espace de noms à ouvrir et d’un point-virgule de fin.

Par exemple,

```qsharp
open Microsoft.Quantum.Canon;
```

Éventuellement, un nom abrégé pour l’espace de noms ouvert peut être défini de sorte que tous les éléments de cet espace de noms puissent (et doivent) être qualifiés par le nom abrégé défini. Un nom de ce type est défini en ajoutant le mot clé `as` suivi du nom abrégé souhaité avant le point-virgule dans une directive `open` :

```qsharp
open Microsoft.Quantum.Math as Math;
```

Toutes les directives de `open` doivent apparaître avant toute déclaration de `function`, `operation`ou `newtype` dans le bloc d’espace de noms.
La directive `open` s’applique à l’intégralité du bloc d’espace de noms dans un fichier.

## <a name="user-defined-type-declarations"></a>Déclarations de types définis par l’utilisateur

Q # offre aux utilisateurs la possibilité de déclarer de nouveaux types définis par l’utilisateur, comme décrit dans la section [Q # type Model](xref:microsoft.quantum.language.type-model) .
Les types définis par l’utilisateur sont distincts même si les types de base sont identiques.
En particulier, il n’existe pas de conversion automatique entre les valeurs de deux types définis par l’utilisateur, même si les types sous-jacents sont identiques.

Une déclaration de type défini par l’utilisateur se compose du mot clé `newtype`, suivi du nom du type défini par l’utilisateur, d’un `=`, d’une spécification de type valide et d’un point-virgule de fin.

Par exemple :

```qsharp
newtype PairOfInts = (Int, Int);
```

Chaque fichier source Q # peut déclarer un nombre quelconque de types définis par l’utilisateur.
Les noms de types doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms d’opération et de fonction.

Il n’est pas possible de définir des dépendances circulaires entre les types définis par l’utilisateur. Les types récursifs ne sont donc pas possibles dans Q #.

## <a name="operation-declarations"></a>Déclarations d’opération

Les opérations sont le cœur de Q #, à peu près analogue aux fonctions dans d’autres langages.
Chaque fichier source Q # peut définir n’importe quel nombre d’opérations.

Les noms d’opérations doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms de type et de fonction.

Une déclaration d’opération se compose du mot clé `operation`, suivi du symbole qui est le nom de l’opération, d’un tuple d’identificateur typé qui définit les arguments de l’opération, d’un signe deux-points `:`, d’une annotation `}`de type qui décrit le type de résultat de l’opération, éventuellement d’une annotation avec les `{`caractéristiques de l’opération

Le corps de la déclaration d’opération se compose de l’implémentation par défaut ou d’une liste de spécialisations.
L’implémentation par défaut peut être spécifiée directement dans la déclaration si seule l’implémentation de la spécialisation du corps par défaut doit être spécifiée explicitement.
Dans ce cas, une annotation avec les caractéristiques de l’opération dans la déclaration est utile pour s’assurer que le compilateur génère automatiquement d’autres spécialisations en fonction de l’implémentation par défaut. 

Par exemple 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

Les caractéristiques de l’opération définissent les genres d’functors qui peuvent être appliqués à l’opération déclarée et leur effet. Si une opération implémente une transformation unitaire, il est possible de définir la façon dont l’opération agit quand *adjointed* ou *contrôlé*.
L’existence de ces spécialisations peut être déclarée dans le cadre de la signature de l’opération. L’implémentation correspondante pour chaque spécialisation déclarée implicitement est ensuite générée par le compilateur. Dans l’exemple ci-dessus, une spécialisation voisine, contrôlée et contrôlée par le compilateur est générée. 

Dans le cas où l’implémentation ne peut pas être générée par le compilateur, elle peut être spécifiée explicitement. Ces déclarations de spécialisation explicites peuvent se composer d’une directive de génération appropriée qui clarifie la manière dont une spécialisation doit être générée, ou d’une implémentation définie par l’utilisateur. Le code de `PrepareEntangledPair` ci-dessus, par exemple, est équivalent au code ci-dessous, contenant des déclarations de spécialisation explicites : 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Le mot clé `auto` indique que le compilateur doit déterminer comment générer l’implémentation de la spécialisation.
Si le compilateur ne peut pas générer l’implémentation pour une certaine spécialisation sans instructions supplémentaires, comme une directive de génération plus précise, ou si une implémentation plus efficace peut être donnée, l’implémentation peut également être définie manuellement.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

Dans l’exemple ci-dessus, `adjoint invert;` indique que la spécialisation voisine doit être générée en inversant l’implémentation du corps, et `controlled adjoint invert;` indique que la spécialisation de la spécialisation voisine doit être générée en inversant l’implémentation donnée de la spécialisation contrôlée.

Pour qu’une opération prenne en charge l’application du `Adjoint` et/ou `Controlled` functor, son type de retour doit obligatoirement être `Unit`. 


### <a name="explicit-specialization-declarations"></a>Déclarations de spécialisation explicites

Les opérations Q # peuvent contenir les déclarations de spécialisation explicites suivantes :

- La spécialisation `body` spécifie l’implémentation de l’opération sans les functors appliqués.
- La spécialisation `adjoint` spécifie l’implémentation de l’opération avec le functor `Adjoint` appliqué.
- La spécialisation `controlled` spécifie l’implémentation de l’opération avec le functor `Controlled` appliqué.
- La spécialisation `controlled adjoint` spécifie l’implémentation de l’opération avec les functors `Adjoint` et `Controlled` appliqués.
  Cette spécialisation peut également être nommée `adjoint controlled`, puisque les deux functors se comportent.


Une spécialisation d’opération se compose de la balise de spécialisation (par exemple, `body`ou `adjoint`, etc.) suivies de l’un des éléments suivants :

- Déclaration explicite comme décrit ci-dessous.
- Directive qui indique au compilateur comment générer la spécialisation, l’un des éléments suivants :
  - `intrinsic`, qui indique que la spécialisation est fournie par l’ordinateur cible.
  - `distribute`, qui peut être utilisé avec les spécialisations `controlled` et `controlled adjoint`.
    Lorsqu’il est utilisé avec `controlled`, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations dans le `body`.
    Lorsqu’il est utilisé avec `controlled adjoint`, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations de la spécialisation `adjoint`.
  - `invert`, qui indique que le compilateur doit calculer la spécialisation `adjoint` en inversant le `body`, c’est-à-dire en inversant l’ordre des opérations et en appliquant le voisin à chacun d’entre eux.
    Lorsqu’il est utilisé avec `adjoint controlled`, cela indique que le compilateur doit calculer la spécialisation en inversant la spécialisation `controlled`.
  - `self`, pour indiquer que la spécialisation voisine est identique à la spécialisation `body`.
    Cela est légal pour les spécialisations `adjoint` et `adjoint controlled`.
    Par `adjoint controlled`, `self` implique que la spécialisation de la `adjoint controlled` est la même que la spécialisation de la `controlled`.
  - `auto`, pour indiquer que le compilateur doit sélectionner une directive appropriée à appliquer.
    `auto` ne peut pas être utilisé pour la spécialisation `body`.

Les directives et les `auto` requièrent tous un point-virgule fermant `;`.
La directive `auto` correspond à la directive de génération suivante si une déclaration explicite du `body` est fournie :

- La spécialisation `adjoint` est générée en fonction de la `invert`de directive.
- La spécialisation `controlled` est générée en fonction de la `distribute`de directive.
- La spécialisation `adjoint controlled` est générée conformément à la directive `invert` si une déclaration explicite pour `controlled` est donnée mais pas pour `adjoint`, et `distribute` dans le cas contraire.

> [!TIP]   
> Si une opération est autonome, spécifiez explicitement l’une ou l’autre de la spécialisation contigut à l’aide de la directive de génération `self` pour permettre au compilateur d’utiliser ces informations à des fins d’optimisation.

Une déclaration de spécialisation contenant une implémentation définie par l’utilisateur se compose d’un tuple d’argument suivi d’un bloc d’instructions avec le code Q # qui implémente la spécialisation.
Dans la liste d’arguments, `...` est utilisé pour représenter les arguments déclarés pour l’opération dans son ensemble.
Pour `body` et `adjoint`, la liste d’arguments doit toujours être `(...)`; pour `controlled` et `adjoint controlled`, la liste d’arguments doit être un symbole qui représente le tableau de qubits de contrôle, suivi par `...`, placé entre parenthèses ; par exemple, `(controls,...)`.

Si une ou plusieurs spécialisations en plus du corps par défaut doivent être déclarées explicitement, l’implémentation du corps par défaut doit également être incluse dans une déclaration de spécialisation appropriée :

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a>Voisin

Le voisin d’une opération spécifie comment la complexe conjugué de l’opération est implémentée, c’est-à-dire comment l’opération agit quand « s’exécute en sens inverse ».
Il est possible de spécifier une opération sans voisin. par exemple, les opérations de mesure n’ont pas de voisin, car elles ne sont pas réversibles.
Une opération prend en charge l' `Adjoint` functor si sa déclaration contient une déclaration implicite ou explicite d’une spécialisation voisine.
Une spécialisation contiguë contrôlée explicitement déclarée implique l’existence d’une spécialisation voisine. 

Pour l’opération dont le corps contient des boucles REPEAT-UNTIL-Successful, des instructions SET, des mesures, des instructions return ou des appels à d’autres opérations qui ne prennent pas en charge l' `Adjoint` functor, la génération automatique d’une spécialisation Join à la suite de la directive `invert` ou `auto` n’est pas possible.

### <a name="controlled"></a>Contrôl

La version contrôlée d’une opération spécifie comment une version contrôlée par Quantum de l’opération est implémentée, c’est-à-dire comment une opération agit quand elle est appliquée à l’état d’un registre Quantum.
Une description plus complète est fournie dans la section [contrôlé](xref:microsoft.quantum.language.type-model#controlled) .

Il est légal de spécifier une opération sans version contrôlée. par exemple, les opérations de mesure n’ont pas de version contrôlée, car elles ne sont pas contrôlable.
Une opération prend en charge l' `Controlled` functor si et seulement si sa déclaration contient une déclaration implicite ou explicite d’une spécialisation contrôlée.
Une spécialisation contiguë contrôlée explicitement déclarée implique l’existence d’une spécialisation contrôlée. 

Pour une opération dont le corps contient des appels à d’autres opérations qui ne prennent pas en charge l' `Controlled` functor, la génération automatique d’une spécialisation contrôlée à la suite de la directive `distribute` ou `auto` n’est pas possible.

### <a name="controlled-adjoint"></a>Contigut contrôlé

La version contrôlée par le contrôle contigut d’une opération spécifie la manière dont une version contrôlée par Quantum de l’opération est implémentée.
Il est possible de spécifier une opération sans contrôle de version voisine. par exemple, les opérations de mesure n’ont pas de version définie par l’utilisateur, car elles ne sont ni contrôlables ni réversibles.

Une spécialisation voisine de l’opération doit exister si et seulement si une spécialisation et une spécialisation contrôlée existent. Dans ce cas, l’existence de la spécialisation voisine contrôlée est déduite et une spécialisation appropriée est générée par le compilateur si aucune implémentation n’a été définie explicitement. 

Pour une opération dont le corps contient des appels à d’autres opérations qui n’ont pas de version définie pour le contrôle joint, la génération automatique d’une spécialisation voisine à la suite de l' `invert`, `distribute` ou `auto` directive n’est pas possible.


### <a name="examples"></a>Exemples

Une déclaration d’opération peut être aussi simple que la suivante, qui définit l’opération Pauli X primitive :

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

Les éléments suivants définissent l’opération de téléopération.

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation PrepareEntangledPair (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        PrepareEntangledPair(target, ancilla);

        // Do the teleportation
        Adjoint PrepareEntangledPair(ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>Déclarations de fonctions

Les fonctions sont des routines purement classiques dans Q #.
Chaque fichier source Q # peut définir un nombre quelconque de fonctions.

Une déclaration de fonction se compose du mot clé `function`, suivi du symbole qui est le nom de la fonction, d’un tuple d’identificateur typé, d’une annotation de type qui décrit le type de retour de la fonction, et d’un bloc d’instructions qui décrit l’implémentation de la fonction.

Le bloc d’instructions définissant une fonction doit être placé dans `{` et `}` comme tout autre bloc d’instructions.

Les noms de fonctions doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms de type et d’opération.
Les fonctions ne peuvent pas allouer ou emprunter des qubits ou appeler des opérations. L’application partielle des opérations ou le passage autour des valeurs de type Operation est parfait.

Par exemple,

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```


## <a name="internal-declarations"></a>Déclarations internes

Les types, les opérations et les fonctions définis par l’utilisateur peuvent également être déclarés comme *internes*.
Cela signifie qu’elles ne sont accessibles qu’à partir du projet Q # dans lequel elles sont déclarées.
Lorsqu’un projet est utilisé comme référence, toutes ses déclarations *publiques* (non internes) sont rendues disponibles, mais toute tentative d’utilisation d’une déclaration interne à partir d’un autre projet génère une erreur.
Les déclarations internes sont utiles pour écrire du code modulaire qui peut être réutilisé par d’autres parties de votre projet, tout en restant modifiable ultérieurement sans arrêter d’autres projets qui peuvent en dépendre.

Un type, une opération ou une fonction interne défini par l’utilisateur peut être déclaré simplement en ajoutant `internal` au début de la déclaration.
Par exemple,

```qsharp
internal newtype PairOfQubits = (Qubit, Qubit);

internal operation PrepareEntangledPair(pair : PairOfQubits) : Unit 
is Adj + Ctl {
    let (q1, q2) = pair!;
    H(q2);
    CNOT(q2, q1);
}

internal function DotProduct(a : Double[], b : Double[]) : Double {
    ...
}
```

> [!WARNING]
> Les types définis par l’utilisateur internes ne peuvent être utilisés que dans des signatures ou des types sous-jacents si le type pouvant être appelé ou défini par l’utilisateur correspondant est également interne.
> Par exemple, s’il existe un type défini par l’utilisateur `InternalOptions` qui a été déclaré avec le mot clé `internal`, les déclarations suivantes génèrent des erreurs :
>
> ```qsharp
> // Error: Can't use InternalOptions as an output type of a public function.
> function DefaultInternalOptions() : InternalOptions { ... }
>
> // Error: Can't use InternalOptions as an item in a public user-defined type.
> newtype ExtendedOptions = (Internal : InternalOptions);
> ```
