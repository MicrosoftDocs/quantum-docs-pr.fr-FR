---
title: 'Instructions Q # | Microsoft Docs'
description: 'Instructions Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9a6f5d53ec21090d0c13f4369e0270d264cd1e9b
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036489"
---
# <a name="statements-and-other-constructs"></a>Instructions et autres constructions

## <a name="comments"></a>Commentaires

Les commentaires commencent par deux barres obliques, `//`et continuent jusqu’à la fin de la ligne.
Un commentaire peut apparaître n’importe où dans un fichier source Q #.

### <a name="documentation-comments"></a>Commentaires sur la documentation

Les commentaires qui commencent par trois barres obliques, `///`, sont traités spécialement par le compilateur lorsqu’ils apparaissent immédiatement avant un espace de noms, une opération, une spécialisation, une fonction ou une définition de type.
Dans ce cas, leur contenu est utilisé comme documentation pour le type pouvant être appelé ou défini par l’utilisateur, comme pour d’autres langages .NET.

Dans `///` commentaires, le texte à afficher dans le cadre de la documentation de l’API est mis en forme en tant que [démarque](https://daringfireball.net/projects/markdown/syntax), avec les différentes parties de la documentation indiquées par des en-têtes spécialement nommés.
En tant qu’extension de la démarque, les références croisées aux opérations, aux fonctions et aux types définis par l’utilisateur dans Q # peuvent être incluses à l’aide de la `@"<ref target>"`, où `<ref target>` est remplacé par le nom qualifié complet de l’objet de code référencé.
Le cas échéant, un moteur de documentation peut également prendre en charge des extensions de démarque supplémentaires.

Par exemple :

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

Les noms suivants sont reconnus en tant qu’en-têtes de commentaires de documentation.

- **Résumé**: bref résumé du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type. Le premier paragraphe du résumé est utilisé pour les informations de survol. Il doit s’agir d’un texte brut.
- **Description**: description du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type. Le résumé et la description sont concaténés pour former le fichier de documentation généré pour la fonction, l’opération ou le type.
  La description peut contenir des équations et des symboles au format LaTeX en ligne.
- **Input**: description du tuple d’entrée d’une opération ou d’une fonction.
  Peut contenir des sous-sections de démarque supplémentaires indiquant chaque élément individuel du tuple d’entrée.
- **Sortie**: description du tuple retourné par une opération ou une fonction.
- **Paramètres de type**: section vide qui contient une sous-section supplémentaire pour chaque paramètre de type générique.
- **Exemple**: exemple bref de l’opération, de la fonction ou du type en cours d’utilisation.
- **Remarques**: divers Proseware décrivant certains aspects de l’opération, de la fonction ou du type.
- **Voir aussi**: liste de noms qualifiés complets indiquant les fonctions connexes, les opérations ou les types définis par l’utilisateur.
- **Références**: liste de références et de citations pour l’élément documenté.

## <a name="namespaces"></a>Espaces de noms

Chaque opération Q #, fonction et type défini par l’utilisateur est défini dans un espace de noms.
Q # suit les mêmes règles d’affectation de noms que d’autres langages .NET.
Toutefois, Q # ne prend pas en charge les références relatives aux espaces de noms.
Autrement dit, si l’espace de noms `a.b` a été ouvert, une référence à des noms d’opérations `c.d` ne sera pas résolue en une opération portant le nom complet `a.b.c.d`.

Dans un bloc d’espace de noms, la directive `open` peut être utilisée pour importer tous les types et callables déclarés dans un espace de noms donné et y faire référence par leur nom non qualifié. Éventuellement, un nom abrégé pour l’espace de noms ouvert peut être défini de sorte que tous les éléments de cet espace de noms puissent (et doivent) être qualifiés par le nom abrégé défini. La directive `open` s’applique à l’intégralité du bloc d’espace de noms dans un fichier.

Un type ou un appelable défini dans un autre espace de noms qui n’est pas ouvert dans l’espace de noms actuel doit être référencé par son nom complet.
Par exemple, une opération nommée `Op` dans l’espace de noms `X.Y` doit être référencée par son nom qualifié complet `X.Y.Op`, sauf si l’espace de noms `X.Y` a été ouvert précédemment dans le bloc actuel. Comme indiqué ci-dessus, même si l’espace de noms `X` a été ouvert, il n’est pas possible de faire référence à l’opération comme `Y.Op`.
Si un nom abrégé `Z` pour `X.Y` a été défini dans cet espace de noms et dans ce fichier, `Op` doit être référencé comme `Z.Op`. 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

Il est généralement préférable d’inclure un espace de noms à l’aide d’une directive `open`.
L’utilisation d’un nom qualifié complet est requise si deux espaces de noms définissent des constructions portant le même nom, et la source actuelle utilise des constructions à partir des deux.

## <a name="formatting"></a>Mise en forme

La plupart des instructions et directives Q # se terminent par un point-virgule de fin, `;`.
Les instructions et les déclarations, telles que `for` et `operation` qui se terminent par un bloc d’instructions, ne nécessitent pas de point-virgule de fin.
Chaque description d’instruction indique si le point-virgule de fin est obligatoire.

Les instructions, comme les expressions, les déclarations et les directives, peuvent être réparties sur plusieurs lignes.
L’utilisation de plusieurs instructions sur une seule ligne doit être évitée.

## <a name="statement-blocks"></a>Blocs d’instructions

Les instructions Q # sont regroupées dans des blocs d’instructions.
Un bloc d’instructions commence par un `{` ouvrant et se termine par un `}`de fermeture.

Un bloc d’instructions placé lexicalement dans un autre bloc est considéré comme un sous-bloc du bloc conteneur. les blocs conteneur et secondaires sont également appelés blocs externes et internes.

## <a name="symbol-binding-and-assignment"></a>Liaison et assignation de symboles

Q # distingue les symboles mutables et immuables.
En général, l’utilisation de symboles immuables est encouragée, car elle permet au compilateur d’effectuer des optimisations supplémentaires.

La partie gauche de la liaison se compose d’un tuple de symboles et de la partie droite d’une expression.

Étant donné que tous les types Q # sont des types valeur, avec le qubits qui prend un rôle un peu spécial, il est formellement créé une « copie » lorsqu’une valeur est liée à un symbole, ou lorsqu’un symbole est relié. Autrement dit, le comportement de Q # est le même que si une copie a été créée lors de l’assignation. En particulier, cela comprend également des tableaux. Bien entendu, dans la pratique, seuls les éléments pertinents sont recréés en fonction des besoins. 

### <a name="tuple-deconstruction"></a>Déconstruction de Tuple

Si le côté droit de la liaison est un tuple, ce tuple peut être déconstruit lors de l’assignation.
Ces déconstructions peuvent impliquer des tuples imbriqués, et toute déconstruction complète ou partielle est valide tant que la forme du tuple sur le côté droit est compatible avec la forme du tuple de symbole.
La déconstruction de tuple peut également être utilisée lorsque le côté droit du `=` est une expression de valeur de Tuple.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Symboles immuables

Les symboles immuables sont liés à l’aide de l’instruction `let`.
Cela équivaut à peu près à la déclaration et à l’initialisation des variables C#dans des langages tels que, sauf que les symboles Q #, une fois liés, ne peuvent pas être modifiés. les liaisons de `let` sont immuables.

Une liaison immuable se compose du mot clé `let`, suivi d’un symbole ou d’un tuple de symboles, d’un signe égal `=`, d’une expression pour lier le ou des symboles à et d’un point-virgule de fin.
Le type du ou des symboles liés est déduit en fonction de l’expression sur le côté droit.

### <a name="mutable-symbols"></a>Symboles mutables

Les symboles mutables sont définis et initialisés à l’aide de l’instruction `mutable`.
Les symboles déclarés et liés dans le cadre d’une instruction `mutable` peuvent être reliés à une valeur différente ultérieurement dans le code. 

Une instruction de liaison mutable se compose du mot clé `mutable`, suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=`, d’une expression pour lier le ou des symboles à et d’un point-virgule de fin.
Le type du ou des symboles liés est déduit en fonction de l’expression sur le côté droit. Si un symbole est relié ultérieurement dans le code, son type ne change pas et la valeur liée doit être compatible avec ce type.

### <a name="rebinding-of-mutable-symbols"></a>Reliaison de symboles mutables

Une variable mutable peut être reliée à l’aide d’une instruction `set`.
Une telle reliaison se compose du mot clé `set`, suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=`, d’une expression pour relier le ou des symboles à et d’un point-virgule de fin.
La valeur doit être compatible avec le ou les types du ou des symboles auxquels elle est liée.

#### <a name="apply-and-reassign-statement"></a>Apply-and-réassign (instruction)

Un type particulier d’instruction SET, que nous appelons instruction Apply-and-réassign, offre un moyen pratique de concaténer si le côté droit est constitué de l’application d’un opérateur binaire et que le résultat doit être relié à l’argument Left à l’opérateur. Par exemple,
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrémente la valeur du compteur `counter` dans chaque itération de la boucle `for`. Le code ci-dessus équivaut à 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
Des instructions similaires sont disponibles pour tous les opérateurs binaires dans lesquels le type du côté gauche correspond au type d’expression. Cela fournit un moyen pratique pour accumuler les valeurs :
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Instruction Update-and-Assign

Une concaténation similaire existe pour les expressions de copie et de mise à jour sur le côté droit. En conséquence, les instructions Update-and-Assign existent pour les éléments nommés dans les types définis par l’utilisateur, ainsi que pour les éléments de tableau.  

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

Dans le cas de tableaux, nos bibliothèques standard contiennent les outils nécessaires pour de nombreux besoins d’initialisation et de manipulation de tableaux courants, et permettent ainsi d’éviter d’avoir à mettre à jour les éléments de tableau en premier lieu. Les instructions Update-and-Assign fournissent une alternative si nécessaire :

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

> [!TIP]   
> Évitez l’utilisation inutile des instructions Update-and-Assign en tirant parti des outils fournis dans <xref:microsoft.quantum.arrays>.

La fonction
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
par exemple, il est simple de simplifier l’utilisation de la fonction `ConstantArray` dans `Microsoft.Quantum.Arrays`, et de retourner une expression de copie et de mise à jour :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a>Portées de liaison

En général, les liaisons de symboles sont hors de portée et deviennent inopérantes à la fin du bloc d’instructions dans lequel elles se produisent.
Il y a deux exceptions à cette règle :

- La liaison de la variable de boucle d’une boucle `for` se trouve dans la portée du corps de la boucle for, mais pas après la fin de la boucle.
- Les trois parties d’une `repeat`/`until` boucle (le corps, le test et la correction) sont traitées comme une seule portée. les symboles liés dans le corps sont donc disponibles dans le test et dans la correction.

Pour les deux types de boucles, chaque passe dans la boucle s’exécute dans sa propre portée, de sorte que les liaisons d’une passe antérieure ne sont pas disponibles dans une étape ultérieure.

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

## <a name="control-flow"></a>Flux de contrôle

### <a name="for-loop"></a>Boucle For

L’instruction `for` prend en charge l’itération sur une plage d’entiers ou sur un tableau.
L’instruction se compose du mot clé `for`, d’une parenthèse ouvrante `(`, suivi d’un symbole ou d’un tuple de symbole, du mot clé `in`, d’une expression de type `Range` ou tableau, d’une parenthèse fermante `)`et d’un bloc d’instructions.

Le bloc d’instructions (corps de la boucle) est exécuté à plusieurs reprises, avec les symboles définis (la ou les variables de boucle) liés à chaque valeur dans la plage ou le tableau.
Notez que si l’expression de plage a la valeur d’une plage ou d’un tableau vide, le corps ne sera pas exécuté.
L’expression est entièrement évaluée avant d’entrer dans la boucle et ne change pas pendant l’exécution de la boucle.

La liaison du ou des symboles déclarés est immuable et suit les mêmes règles que les autres liaisons de variables. En particulier, il est possible de détruire, par exemple, les éléments de tableau pour une itération sur un tableau lors de l’assignation à la ou aux variables de boucle.

Par exemple,

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

La variable de boucle est liée à chaque entrée dans le corps de la boucle et est détachée à la fin du corps.
En particulier, la variable de boucle n’est pas liée après la fin de la boucle for.

### <a name="repeat-until-success-loop"></a>Répéter jusqu’à la réussite de la boucle

L’instruction `repeat` prend en charge le modèle Quantum « répéter jusqu’à la réussite ».
Il se compose du mot clé `repeat`, suivi d’un bloc d’instructions (corps de la _boucle_ ), du mot clé `until`, d’une expression booléenne et d’un point-virgule de fin ou du mot clé `fixup` suivi d’un autre bloc d’instructions (la _Correction_).
Le corps de la boucle, la condition et la correction sont tous considérés comme une seule étendue, de sorte que les symboles liés dans le corps sont disponibles dans la condition et la correction.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

Le corps de la boucle est exécuté, puis la condition est évaluée.
Si la condition est true, l’instruction est terminée ; dans le cas contraire, la correction est exécutée et l’instruction est réexécutée en commençant par le corps de la boucle.
Notez que l’exécution de la correction met fin à l’étendue de l’instruction, de sorte que les liaisons de symboles effectuées pendant le corps ou la correction ne sont pas disponibles dans les répétitions suivantes.

Par exemple, le code suivant est un circuit probabiliste qui implémente une porte de rotation importante $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ à l’aide des portes Hadarmard et T.
La boucle se termine dans $ \frac{8}{5}$ répétitions en moyenne.
Pour plus d’informations, consultez [*répéter jusqu’à la réussite : décomposition non déterministe des unités de qubit de données uniques*](https://arxiv.org/abs/1311.1074) (Paetznick et Svore, 2014).

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

> [!TIP]   
> Évitez d’utiliser des boucles de répétition jusqu’à réussite dans les fonctions. Les fonctionnalités correspondantes sont fournies par les boucles While dans les fonctions. 

### <a name="while-loop"></a>Boucle while

Les modèles de répétition jusqu’à réussite ont un connotation très spécifique au quantum. Elles sont largement utilisées dans des classes particulières d’algorithmes Quantum, donc la construction du langage dédié dans Q #. Toutefois, les boucles qui s’arrêtent en fonction d’une condition et dont la longueur d’exécution est donc inconnue au moment de la compilation doivent être gérées avec une attention particulière dans un Runtime Quantum. Leur utilisation dans les fonctions en revanche pose un problème, car celles-ci contiennent uniquement du code qui sera exécuté sur du matériel conventionnel (non Quantum). 

Q # prend donc en charge l’utilisation de boucles While uniquement dans les fonctions. Une instruction `while` se compose du mot clé `while`, d’une parenthèse ouvrante `(`, d’une condition (c’est-à-dire une expression booléenne), d’une parenthèse fermante `)`et d’un bloc d’instructions.
Le bloc d’instructions (corps de la boucle) est exécuté tant que la condition a la valeur `true`.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Instruction conditionnelle

L’instruction `if` prend en charge l’exécution conditionnelle.
Il se compose du mot clé `if`, d’une parenthèse ouvrante `(`, d’une expression booléenne, d’une parenthèse fermante `)`et d’un bloc d’instructions (bloc _Then_ ).
Il peut être suivi d’un nombre quelconque de clauses Else-If, chacune comprenant le mot clé `elif`, une parenthèse ouvrante `(`, une expression booléenne, une parenthèse fermante `)`et un bloc d’instructions (le bloc _else-if_ ).
Enfin, l’instruction peut éventuellement se terminer par une clause Else, qui se compose du mot clé `else` suivi d’un autre bloc d’instructions (le bloc _else_ ).
La condition est évaluée, et si elle a la valeur true, le bloc Then est exécuté.
Si la condition est false, la première condition else-if est évaluée ; Si la valeur est true, le bloc Else-If est exécuté.
Dans le cas contraire, le deuxième bloc Else-If est testé, puis le troisième, et ainsi de suite jusqu’à ce qu’une clause avec une condition true soit rencontrée ou qu’il n’y ait plus aucune clause else-if.
Si la condition if d’origine et toutes les clauses Else-If ont la valeur false, le bloc Else est exécuté s’il en a été fourni.

Notez que le bloc qui est exécuté est exécuté dans sa propre portée.
Les liaisons effectuées à l’intérieur d’un bloc Then, else-if ou Else ne sont pas visibles après la fin de l’instruction if.

Par exemple,

```qsharp
if (result == One) {
    X(target);
} 
```

or

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>Renvoie

L’instruction return termine l’exécution d’une opération ou d’une fonction et retourne une valeur à l’appelant.
Il se compose du mot clé `return`, suivi d’une expression du type approprié et d’un point-virgule de fin.

Un pouvant être appelé qui retourne un tuple vide, `()`, ne requiert pas d’instruction return.
Si vous souhaitez une sortie précoce, `return ()` peut être utilisée dans ce cas.
Les callables qui retournent tout autre type requièrent une instruction return finale.

Il n’y a pas de nombre maximal d’instructions return dans une opération.
Le compilateur peut émettre un avertissement si les instructions suivent une instruction return dans un bloc.

Par exemple,

```qsharp
return 1;
```

or

```qsharp
return ();
```

or

```qsharp
return (results, qubits);
```

### <a name="fail"></a>Échec

L’instruction Fail termine l’exécution d’une opération et retourne une valeur d’erreur à l’appelant.
Il se compose du mot clé `fail`, suivi d’une chaîne et d’un point-virgule de fin.
La chaîne est retournée au pilote classique comme message d’erreur.

Il n’existe aucune restriction sur le nombre d’instructions d’échec au sein d’une opération.
Le compilateur peut émettre un avertissement si les instructions suivent une instruction Fail dans un bloc.

Par exemple,

```qsharp
fail $"Impossible state reached";
```

or

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Gestion de qubit

Notez qu’aucune de ces instructions n’est autorisée dans le corps d’une fonction.
Elles ne sont valides que dans les opérations.

### <a name="clean-qubits"></a>Nettoyer qubits

L’instruction `using` permet d’acquérir de nouvelles qubits à utiliser lors d’un bloc d’instructions.
Les qubits sont assurés d’être initialisés à l’état de `Zero` de calcul.
Le qubits doit être dans l’état de `Zero` de calcul à la fin du bloc d’instructions ; les simulateurs sont encouragés à appliquer cela.

L’instruction se compose du mot clé `using`, suivi d’une parenthèse ouvrante `(`, d’une liaison, d’une parenthèse fermante `)`et du bloc d’instructions dans lequel qubits sera disponible.
La liaison suit le même modèle que `let` instructions : un symbole unique ou un tuple de symboles, suivi d’un signe égal `=`et une valeur unique ou un tuple correspondant d’initialiseurs.
Les initialiseurs sont disponibles pour un qubit unique, indiqué comme `Qubit()`, ou un tableau de qubits, indiqué par `Qubit[`, une expression `Int` et `]`.

Par exemple,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a>Qubits empruntés

L’instruction `borrowing` permet d’obtenir des qubits pour une utilisation temporaire. L’instruction se compose du mot clé `borrowing`, suivi d’une parenthèse ouvrante `(`, d’une liaison, d’une parenthèse fermante `)`et du bloc d’instructions dans lequel qubits sera disponible.
La liaison suit le même modèle et les mêmes règles que celle d’une instruction `using`.

Par exemple,

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

Le qubits emprunté est dans un état inconnu et est hors de portée à la fin du bloc d’instructions.
L’emprunteur s’engage à laisser le qubits dans le même État que celui dans lequel il se trouvait lorsqu’il a été emprunté, c’est-à-dire que son état au début et à la fin du bloc d’instructions est supposé être le même.
En particulier, cet État n’est pas nécessairement un État classique, ce qui signifie que dans la plupart des cas, les étendues d’emprunt ne doivent pas contenir de mesures. 

Pour obtenir un exemple d’utilisation Svore empruntée, voir [*factorisation à l’aide de 2n + 2 qubits avec la multiplication modulaire basée sur Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler et qubit 2017).

Lorsque vous empruntez des qubits, le système tente d’abord de remplir la demande à partir de qubits qui sont en cours d’utilisation, mais qui ne sont pas accessibles pendant le corps de l’instruction `borrowing`.
S’il n’y a pas suffisamment de qubits, il allouera de nouvelles qubits pour terminer la demande.

## <a name="conjugations"></a>Conjugaisons

Contrairement aux bits classiques, la libération de la mémoire Quantum est un peu plus complexe, car la réinitialisation aveugle de qubits peut avoir des effets indésirables sur le calcul restant si les qubits sont toujours pris en compte. Cela peut être évité en « annulant » les calculs effectués avant la libération de la mémoire. Un modèle courant dans quantum computing est donc le suivant : 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

: nouveauté : à partir de notre version 0,9, nous prenons en charge une instruction de conjugaison qui implémente la transformation ci-dessus. À l’aide de cette instruction, l’opération `ApplyWith` peut être implémentée de la façon suivante :

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Une telle instruction de conjugaison devient évidemment beaucoup plus utile si les transformations externes et internes ne sont pas facilement disponibles en tant qu’opérations, mais sont plutôt plus pratiques à décrire par un bloc composé de plusieurs instructions. 

La transformation inverse pour les instructions définies dans le bloc intérieur est générée automatiquement par le compilateur et exécutée après la fin du bloc apply. Étant donné que toutes les variables mutables utilisées dans le cadre du bloc within ne peuvent pas être reliées dans le bloc Apply, il est garanti que la transformation générée est le voisin du calcul dans le bloc intérieur. 

## <a name="expression-evaluation-statements"></a>Instructions d’évaluation d’expression

Toute expression d’appel de type `Unit` peut être utilisée en tant qu’instruction.
Cela est principalement utilisé lors de l’appel d’opérations sur des qubits qui retournent `Unit`, car l’objectif de l’instruction est de modifier l’État Quantum implicite.
Les instructions d’évaluation d’expression requièrent un point-virgule de fin.

Par exemple,

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
