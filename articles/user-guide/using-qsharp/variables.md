---
title: Variables dans Q#
description: En savoir plus sur l’utilisation de différentes variables dans Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb87f36d3c9b7df195f64e85151e833d494ea945
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835874"
---
# <a name="variables-in-no-locq"></a>Variables dans Q#

Q# distingue les symboles mutables et immuables, ou les *variables*, qui sont liées/affectées aux expressions.
En général, l’utilisation de symboles immuables est encouragée, car elle permet au compilateur d’effectuer des optimisations supplémentaires.

La partie gauche d’une liaison se compose d’un tuple de symboles et de la partie droite d’une expression.

## <a name="immutable-variables"></a>Variables immuables

Vous pouvez affecter une valeur de n’importe quel type dans Q# à une variable en vue de sa réutilisation au sein d’une opération ou d’une fonction à l’aide du `let` mot clé. 

Une liaison immuable se compose du mot clé `let` , suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=` , d’une expression pour lier le ou des symboles à et d’un point-virgule de fin.

Exemple :

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Cela affecte un tableau particulier d’opérateurs Pauli au nom de la variable (ou « Symbol »), `measurementOperator` .

> [!NOTE]
> Dans l’exemple précédent, il n’est pas nécessaire de spécifier explicitement le type de la nouvelle variable, car l’expression sur le côté droit de l' `let` instruction n’est pas ambiguë et le compilateur déduit le type correct. 

Les variables définies à l’aide de `let` sont *immuables*, ce qui signifie qu’une fois que vous l’avez définie, vous ne pouvez plus la modifier.
Cela permet d’effectuer plusieurs optimisations bénéfiques, notamment l’optimisation de la logique classique qui agit sur les variables à réorganiser pour l’application `Adjoint` de la variante d’une opération.

## <a name="mutable-variables"></a>Variables mutables

En guise d’alternative à la création d’une variable avec `let` , le `mutable` mot clé crée une variable mutable qui *peut* être reliée après sa création initiale à l’aide du `set` mot clé.

Vous pouvez relier les symboles déclarés et liés dans le cadre d’une `mutable` instruction à une valeur différente ultérieurement dans le code. Si un symbole est relié ultérieurement dans le code, son type ne change pas et la valeur qui vient d’être liée doit être compatible avec ce type.

### <a name="rebinding-of-mutable-symbols"></a>Reliaison de symboles mutables

Vous pouvez relier une variable mutable à l’aide d’une `set` instruction.
Une telle reliaison se compose du mot clé `set` , suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=` , d’une expression pour relier le ou des symboles à, et d’un point-virgule de fin.

Voici quelques exemples de techniques d’instruction de reliaison.

#### <a name="apply-and-reassign-statements"></a>Instructions Apply-and-réassign

Un genre particulier d' `set` instruction, l’instruction *apply-and-réassign* , offre un moyen pratique de concaténer si le côté droit est constitué de l’application d’un opérateur binaire, et le résultat doit être relié à l’argument Left à l’opérateur. Par exemple,

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrémente la valeur du compteur `counter` dans chaque itération de la `for` boucle. Le code précédent est équivalent à 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Des instructions similaires sont disponibles pour tous les opérateurs binaires dans lesquels le type du côté gauche correspond au type d’expression. Ces instructions offrent un moyen pratique d’accumuler des valeurs.

Par exemple, supposons qu' `qubits` il s’agit d’un registre de qubits :
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Instructions Update-and-Assign

Une concaténation similaire existe pour les [expressions de copie et de mise à jour](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) sur le côté droit.
En conséquence, les instructions *Update-and-Assign* existent pour les *éléments nommés* dans les types définis par l’utilisateur, ainsi que pour les *éléments de tableau*.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

Dans le cas de tableaux, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) dans la Q# bibliothèque standard fournit les outils nécessaires pour de nombreux besoins d’initialisation et de manipulation de tableau communs, ce qui permet d’éviter d’avoir à mettre à jour les éléments de tableau en premier lieu. 

Les instructions Update-and-Assign fournissent une alternative si nécessaire :

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

À l’aide des outils de bibliothèque pour les tableaux fournis dans [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , vous pouvez, par exemple, définir facilement une fonction qui retourne un tableau de `Pauli` types où l’élément à l’index `i` prend une `Pauli` valeur donnée, et toutes les autres entrées sont l’identité ( `PauliI` ).

Voici deux définitions d’une telle fonction, avec la seconde tirant parti des outils de notre disposition.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

Au lieu d’effectuer une itération au sein de chaque index du tableau, et de le définir de manière conditionnelle sur `PauliI` ou sur le donné `pauli` , vous pouvez utiliser à la place de `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) pour créer un tableau de `PauliI` types, puis simplement retourner une expression de copie et de mise à jour dans laquelle vous avez modifié la valeur spécifique au niveau de l’index `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Déconstruction de Tuple

Outre l’affectation d’une variable unique, vous pouvez utiliser les `let` `mutable` Mots clés et, ou toute autre construction de liaison, telle que `set` -pour décompresser le contenu d’un [type de tuple](xref:microsoft.quantum.guide.types#tuple-types).
Une assignation de ce formulaire est dite pour *déconstruire* les éléments de ce tuple.

Si le côté droit de la liaison est un tuple, vous pouvez déconstruire ce tuple lors de l’assignation.
Ces déconstructions peuvent impliquer des tuples imbriqués, et toute déconstruction complète ou partielle est valide tant que la forme du tuple sur le côté droit est compatible avec la forme du tuple de symbole.

Par exemple :

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Portées de liaison

En général, les liaisons de symboles sont hors de portée et deviennent inopérantes à la fin du bloc d’instructions dans lequel elles se produisent.
Il y a deux exceptions à cette règle :

- La liaison de la variable de boucle d’une `for` boucle est dans la portée du corps de la boucle for, mais pas après la fin de la boucle.
- Les trois parties d’une `repeat` / `until` boucle (le corps, le test et la correction) agissent en tant qu’étendue unique, de sorte que les symboles qui sont liés dans le corps sont disponibles dans le test et la correction.

Pour les deux types de boucles, chaque passage à la boucle s’exécute dans sa propre portée, de sorte que les liaisons d’une passe antérieure ne sont pas disponibles dans une étape ultérieure.
Pour plus d’informations sur ces boucles, consultez [Control Flow](xref:microsoft.quantum.guide.controlflow).

Les blocs internes héritent des liaisons de symboles des blocs externes.
Vous ne pouvez lier un symbole qu’une seule fois par bloc ; Il est interdit de définir un symbole portant le même nom qu’un autre symbole dans la portée (sans « occultation »).
Les séquences suivantes sont valides :

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

et

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

Mais cela ne serait pas conforme :

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

comme cela :

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a>Étapes suivantes

En savoir plus sur l' [utilisation de qubits](xref:microsoft.quantum.guide.qubits) dans Q# .