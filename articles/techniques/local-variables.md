---
title: 'Variables locales-techniques Q #'
description: 'Découvrez comment définir et utiliser des variables locales dans Q #.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: cb6c662137c31a13c3dd6e9ca3f67879c469f788
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906863"
---
# <a name="local-variables"></a>Variables locales #

Une valeur de n’importe quel type dans Q # peut être assignée à une variable pour être réutilisée au sein d’une opération ou d’une fonction à l’aide du mot clé `let`.
Exemple :

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Cela affecte un tableau particulier d’opérateurs Pauli à une variable appelée `measurementOperator`.

> [!TIP]
> Notez que nous n’avons pas besoin de spécifier explicitement le type de notre nouvelle variable, car l’expression sur le côté droit de l’instruction `let` n’est pas ambiguë et le type est déduit par le compilateur. 

Les variables dans Q # sont *immuables*, ce qui signifie qu’une fois qu’une variable a été définie de cette façon, elle ne peut plus être modifiée.
Cela permet d’effectuer plusieurs optimisations bénéfiques, notamment l’optimisation de la logique classique agissant sur les variables à réorganiser pour l’application de la `Adjoint` variante d’une opération.

Les variables définies à l’aide de la liaison `let` comme ci-dessus sont locales à une portée particulière, telles que le corps d’une opération ou le contenu d’une boucle `for`.


## <a name="mutability"></a>Mutabilité ##

En guise d’alternative à la création d’une variable avec `let`, le mot clé `mutable` crée une variable mutable spéciale qui peut être reliée après sa création initiale à l’aide du mot clé `set`.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Tous les types dans Q #, y compris les tableaux, suivent la sémantique des valeurs. En particulier, il n’est pas possible de mettre à jour les éléments d’un tableau. Pour modifier un tableau existant, vous devez tirer parti d’un mécanisme de copie et de mise à jour semblable à F#celui des enregistrements dans. À l’aide des outils de bibliothèque pour les tableaux fournis dans [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), nous pouvons, par exemple, définir facilement une fonction qui retourne un tableau de Paulis où le Pauli à l’index `i` prend la valeur donnée et toutes les autres entrées sont l’identité : 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

Nous étudierons plus en détail l’utilisation des tableaux lors de l’examen des instructions et expressions Q #. 

La mutabilité dans Q # est un concept qui s’applique à un *symbole* plutôt qu’à un type ou une valeur. Plus précisément, il n’a pas de représentation dans le système de type, implicitement ou explicitement, et si une liaison est mutable (comme indiqué par le mot clé `mutable`) ou immuable (comme indiqué par `let`) ne modifie pas le type de la ou des variables liées. Cela offre un moyen important d’isoler la mutabilité dans des fonctions et des opérations spécialisées.
En particulier, même si une spécialisation voisine d’une opération qui utilise une variable mutable ne peut pas être générée automatiquement, la génération automatique fonctionne correctement pour une opération qui appelle une fonction qui utilise mutabilité.
Pour cette raison, il est recommandé de faire en sorte que les fonctions et les opérations qui utilisent la mutabilité soient courtes et compactes, afin que le reste du programme Quantum puisse être écrit à l’aide de variables immuables ordinaires.


## <a name="deconstruction"></a>Déconstruction ##

Outre l’affectation d’une seule variable, les mots clés `let` et `mutable`, ou en fait, toute autre construction de liaison, permettent également de décompresser le contenu d’un [type de tuple](xref:microsoft.quantum.language.type-model#tuple-types).
Une assignation de ce formulaire est dite pour *déconstruire* les éléments de ce tuple.
Par exemple, si nous modélisons un terme dans un même lieu par un tuple, nous pouvons utiliser la déconstruction pour accéder aux différentes données que nous devons simuler sous ce terme :

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


