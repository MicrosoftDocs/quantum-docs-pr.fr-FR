---
title: 'En savoir plus sur les techniques Q #'
description: 'Explorez des rubriques avancées dans Q #, telles que la création de fonctions génériques et l’emprunt de qubits.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: 46ebf544c1d6e56f152a06d06151305fa972011a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906897"
---
# <a name="going-further"></a>Aller plus loin #

Maintenant que vous avez vu comment écrire des programmes quantiques intéressants dans Q #, cette section va plus loin en introduisant des rubriques plus avancées qui doivent se révéler utiles.


## <a name="generic-operations-and-functions"></a>Opérations et fonctions génériques ##

> [!TIP]
> Cette section suppose une connaissance de base des [génériques dans C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), des [génériques dans F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ des modèles](https://docs.microsoft.com/cpp/cpp/templates-cpp)ou des approches similaires à la surprogrammation dans d’autres langages.

De nombreuses fonctions et opérations que nous pouvons souhaiter définir ne s’appuient pas vraiment sur les types de leurs entrées, mais plutôt implicitement utiliser leurs types via une autre fonction ou opération.
Par exemple, considérez le concept de *carte* commun à de nombreux langages fonctionnels ; à partir d’une fonction $f (x) $ et d’une collection de valeurs $\{x_1, x_2, \dots, x_n\}$, Map retourne une nouvelle collection $\{f (x_1), f (x_2), \dots, f (x_n)\}$.
Pour l’implémenter dans Q #, nous pouvons tirer parti de la première classe de ces fonctions.
Nous allons écrire un exemple rapide de `Map`, en utilisant ★ en tant qu’espace réservé tout en décrivant les types dont nous avons besoin.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Remarque Cette fonction est très similaire, quel que soit le type réel que nous remplaçons.
Une carte des entiers à Paulis, par exemple, est similaire à une carte à partir de nombres à virgule flottante en chaînes :

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

En principe, nous pourrions écrire une version de `Map` pour chaque paire de types que nous rencontrons, mais cela introduit un certain nombre de difficultés.
Par exemple, si nous trouvons un bogue dans `Map`, nous devons nous assurer que le correctif est appliqué uniformément dans toutes les versions de `Map`.
De plus, si nous construisons un nouveau tuple ou UDT, nous devons maintenant créer également un nouveau `Map` pour aller avec le nouveau type.
Bien que cela soit tractable pour un petit nombre de ces fonctions, étant donné que nous recueillons de plus en plus de fonctions de la même forme que `Map`, le coût de l’introduction de nouveaux types devient insuffisant dans un ordre relativement court.

Toutefois, une grande partie de cette difficulté est que nous n’avons pas donné au compilateur les informations dont il a besoin pour reconnaître comment les différentes versions de `Map` sont associées.
En fait, nous voulons que le compilateur traite `Map` comme un type de fonction mathématique des *types* q # aux fonctions q #.
Cette notion est formalisée en autorisant les fonctions et les opérations à avoir des *paramètres de type*, ainsi que leurs paramètres de tuple ordinaires.
Dans les exemples ci-dessus, nous souhaitons considérer `Map` comme ayant des paramètres de type `Int, Pauli` dans le premier cas et `Double, String` dans le second cas.
Dans la plupart des cas, ces paramètres de type peuvent ensuite être utilisés comme s’il s’agissait de types ordinaires : nous utilisons des valeurs de paramètres de type pour créer des tableaux et des tuples, appeler des fonctions et des opérations, et les assigner à des variables ordinaires ou mutables.

> [!NOTE]
> Le cas le plus extrême de dépendance indirecte est le cas de qubits, où un programme Q # ne peut pas s’appuyer directement sur la structure du type de `Qubit`, mais **doit** passer ces types à d’autres opérations et fonctions.

En revenant à l’exemple ci-dessus, nous pouvons voir que nous avons besoin de `Map` pour avoir des paramètres de type, l’un pour représenter l’entrée à `fn` et l’autre pour représenter la sortie de `fn`.
Dans Q #, il est écrit en ajoutant des crochets pointus (`<>`, et non brakets $ \braket{}$ !) après le nom d’une fonction ou d’une opération dans sa déclaration, et en répertoriant chaque paramètre de type.
Le nom de chaque paramètre de type doit commencer par un cycle `'`, indiquant qu’il s’agit d’un paramètre de type et non d’un type ordinaire (également appelé type *concret* ).
Par `Map`, nous écrivons donc :

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Notez que la définition de `Map<'Input, 'Output>` semble très similaire aux versions que nous avons écrites auparavant.
La seule différence est que nous avons explicitement informé le compilateur que `Map` ne dépend pas directement des `'Input` et des `'Output`, mais fonctionne pour deux types quelconques en les utilisant indirectement par le biais de `fn`.
Une fois que nous avons défini `Map<'Input, 'Output>` de cette manière, nous pouvons l’appeler comme s’il s’agissait d’une fonction ordinaire :

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> L’écriture de fonctions et d’opérations génériques est un emplacement où « tuple en sortie de tuple » est un moyen très utile de réfléchir aux fonctions et opérations Q #.
> Étant donné que chaque fonction accepte exactement une entrée et retourne exactement une sortie, une entrée de type `'T -> 'U` correspond à *n’importe quelle* fonction Q # de quelque manière que ce soit.
> De même, toute opération peut être passée à une entrée de type `'T => 'U`.

En guise de deuxième exemple, considérez le défi que pose l’écriture d’une fonction qui retourne la composition de deux autres fonctions :

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Ici, nous devons spécifier exactement ce que `A`, `B`et `C` sont, par conséquent, il est donc nécessaire de limiter gravement l’utilitaire de notre nouvelle fonction `Compose`.
Après tout, `Compose` dépend de `A`, `B`et `C` *via* `innerFn` et `outerFn`.
En guise d’alternative, nous pouvons ajouter des paramètres de type à `Compose` indiquant qu’elle fonctionne pour *n’importe quel* `A`, `B`et `C`, tant que ces paramètres correspondent à ceux attendus par `innerFn` et `outerFn`:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Les bibliothèques standard Q # fournissent une série de ces opérations et fonctions paramétrées de type pour faciliter l’utilisation du workflow de contrôle d’ordre supérieur.
Celles-ci sont abordées plus en détail dans le Guide de la [bibliothèque standard Q #](xref:microsoft.quantum.libraries.standard.intro).

## <a name="borrowing-qubits"></a>Emprunt d’qubits ##

Le mécanisme d’emprunt autorise l’allocation de qubits qui peut être utilisé comme espace de travail pendant un calcul. Ces qubits ne sont généralement pas dans un état propre, c’est-à-dire qu’ils ne sont pas nécessairement initialisés dans un état connu tel que $ \ket{0}$. L’un d’eux parle également de « qubits », car leur état est inconnu et peut même être enchevêtré avec d’autres parties de la mémoire de l’ordinateur quantique. Parmi les cas d’utilisation connus des qubits modifiés, citons les implémentations de portes CNOTIN multicontrôlées qui requièrent uniquement très peu de qubits et l’implémentation d’incrémenteurs.

Dans l’Canon, il existe des exemples qui utilisent le mot clé `borrowing`, par exemple la fonction `MultiControlledXBorrow` définie ci-dessous.
Si `controls` dénote le contrôle qubits qui doit être ajouté à une opération de `X`, alors l’ensemble de `Length(controls)-2` de ancillas modifiés sera ajouté par cette implémentation.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Notez que l’utilisation intensive du combineur `With`---dans sa forme applicable pour les opérations qui prennent en charge l’ajout de voisins, c’est-à-dire `WithA`---a été effectuée dans cet exemple, qui est un bon style de programmation, car l’ajout d’un contrôle aux structures impliquant `With` ne propage le contrôle à l’opération interne. Notez également que, en plus de la `body` de l’opération, une implémentation du corps `controlled` de l’opération a été explicitement fournie, plutôt que de recourir à une instruction `controlled auto`. Cela est dû au fait que nous savons à partir de la structure du circuit comment ajouter facilement des contrôles supplémentaires, ce qui est avantageux par rapport à l’ajout de contrôle à chaque porte de la `body`. 

Il est intéressant de comparer ce code avec une autre fonction Canon `MultiControlledXClean` qui atteint le même objectif de l’implémentation d’une opération `X` à contrôle multiple, mais qui utilise plusieurs qubits propres à l’aide du mécanisme de `using`. 
