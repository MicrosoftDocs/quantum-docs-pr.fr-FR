---
title: 'Variables dans Q #'
description: Description de remplissage
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 456c05d4ca66a747e0cc514a30c6bbb33610f481
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327779"
---
# <a name="variables-in-q"></a>Variables dans Q #

Q # permet de faire la distinction entre les symboles mutables et immuables, ou les « variables », qui sont liés/assignés à des expressions.
En général, l’utilisation de symboles immuables est encouragée, car elle permet au compilateur d’effectuer des optimisations supplémentaires.

La partie gauche d’une liaison se compose d’un tuple de symboles et de la partie droite d’une expression.

## <a name="immutable-variables"></a>Variables immuables

Une valeur de tout type dans Q # peut être assignée à une variable pour être réutilisée au sein d’une opération ou d’une fonction à l’aide du `let` mot clé.

Une liaison immuable se compose du mot clé `let` , suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=` , d’une expression pour lier le ou des symboles à et d’un point-virgule de fin.

Exemple :

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Cela affecte un tableau particulier d’opérateurs Pauli au nom de la variable (ou « Symbol »), `measurementOperator` .

> [!NOTE]
> Nous n’avons pas besoin de spécifier explicitement le type de notre nouvelle variable, car l’expression sur le côté droit de l' `let` instruction n’est pas ambiguë et le type est déduit par le compilateur. 

Les variables définies à l’aide de `let` sont *immuables*, ce qui signifie qu’une fois qu’elle a été définie, elle ne peut plus être modifiée.
Cela permet d’effectuer plusieurs optimisations bénéfiques, notamment l’optimisation de la logique classique agissant sur les variables à réorganiser pour l’application `Adjoint` de la variante d’une opération.

## <a name="mutable-variables"></a>Variables mutables

En guise d’alternative à la création d’une variable avec `let` , le `mutable` mot clé crée une variable mutable qui *peut* être reliée après sa création initiale à l’aide du `set` mot clé.

Les symboles déclarés et liés dans le cadre d’une `mutable` instruction peuvent être reliés à une valeur différente ultérieurement dans le code. Si un symbole est relié ultérieurement dans le code, son type ne change pas et la valeur qui vient d’être liée doit être compatible avec ce type.

### <a name="rebinding-of-mutable-symbols"></a>Reliaison de symboles mutables

Une variable mutable peut être reliée à l’aide d’une `set` instruction.
Une telle reliaison se compose du mot clé `set` , suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=` , d’une expression pour relier le ou des symboles à, et d’un point-virgule de fin.

Ici, nous fournissons des exemples possibles de techniques d’instruction de reliaison

### <a name="apply-and-reassign-statements"></a>Instructions Apply-and-réassign

Un genre d’instruction particulière, `set` que nous appelons instruction *apply-and-réassign* , offre un moyen pratique de concaténation si le côté droit est constitué de l’application d’un opérateur binaire et que le résultat doit être relié à l’argument Left à l’opérateur. Par exemple,
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrémente la valeur du compteur `counter` dans chaque itération de la `for` boucle. Le code ci-dessus équivaut à 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Des instructions similaires sont disponibles pour tous les opérateurs binaires dans lesquels le type du côté gauche correspond au type d’expression. Cela fournit un moyen pratique pour accumuler des valeurs.

Par exemple, supposons qu' `qubits` il s’agit d’un regsiter de qubits :
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a>Instructions Update-and-Assign

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

Dans le cas de tableaux, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) dans nos bibliothèques standard fournit les outils nécessaires pour de nombreux besoins d’initialisation et de manipulation de tableau communs, ce qui vous évite d’avoir à mettre à jour les éléments de tableau en premier lieu. 

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

À l’aide des outils de bibliothèque pour les tableaux fournis dans [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , nous pouvons, par exemple, définir facilement une fonction qui retourne un tableau de Paulis où le Pauli à l’index `i` prend la valeur donnée et toutes les autres entrées sont l’identité.

Voici deux définitions d’une telle fonction, avec la seconde tirant parti des outils de notre disposition.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

Au lieu d’effectuer une itération sur chaque index du tableau et de lui affecter la `PauliI` `Pauli` valeur ou, nous pouvons utiliser `ConstantArray` à [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) la place pour créer un tableau de `PauliI` , puis retourner simplement une expression copy-and-Update dans laquelle nous avons modifié la valeur spécifique à l’index `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Déconstruction de Tuple

Outre l’affectation d’une variable unique, les `let` `mutable` Mots clés et---ou en fait toute autre construction de liaison, telle que `set` (décrite ci-dessous)---également permettre la décompression du contenu d’un [type de tuple](xref:microsoft.quantum.guide.types#tuple-types).
Une assignation de ce formulaire est dite pour *déconstruire* les éléments de ce tuple.

Si le côté droit de la liaison est un tuple, ce tuple peut être déconstruit lors de l’assignation.
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
- Les trois parties d’une `repeat` / `until` boucle (le corps, le test et la correction) sont traitées comme une seule étendue, de sorte que les symboles qui sont liés dans le corps sont disponibles dans le test et dans la correction.

Pour les deux types de boucles, chaque passe dans la boucle s’exécute dans sa propre portée, de sorte que les liaisons d’une passe antérieure ne sont pas disponibles dans une étape ultérieure.
Pour plus d’informations sur ces boucles, consultez [Flow Control](xref:microsoft.quantum.guide.controlflow).

Les liaisons de symboles des blocs externes sont héritées par les blocs internes.
Un symbole ne peut être lié qu’une seule fois par bloc ; Il est interdit de définir un symbole portant le même nom qu’un autre symbole dans la portée (sans « occultation »).
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

and

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

En savoir plus sur l' [utilisation de qubits](xref:microsoft.quantum.guide.qubits) dans Q #.