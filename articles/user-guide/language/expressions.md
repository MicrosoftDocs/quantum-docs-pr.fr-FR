---
title: Expressions dans Q#
description: Comprenez comment spécifier, référencer et combiner des constantes, des variables, des opérateurs, des opérations et des fonctions en tant qu’expressions dans Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: e95a7cb9b74136ef9a6f51b4bbc32d1d93c43a0d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691591"
---
# <a name="expressions-in-no-locq"></a>Expressions dans Q#

## <a name="numeric-expressions"></a>Expressions numériques

Les expressions numériques sont des expressions de type `Int` , `BigInt` ou `Double` .
Autrement dit, il s’agit de nombres entiers ou à virgule flottante.

`Int` les littéraux dans Q# sont écrits sous la forme d’une séquence de chiffres.
Les entiers hexadécimaux et binaires sont pris en charge et écrits avec un `0x` `0b` préfixe et, respectivement.

`BigInt` les littéraux dans Q# ont un `l` suffixe ou de fin `L` .
Les entiers hexadécimaux Big sont pris en charge et écrits avec un préfixe « 0x ».
Par conséquent, Voici toutes les utilisations valides des `BigInt` littéraux :

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` les littéraux dans Q# sont des nombres à virgule flottante écrits à l’aide de chiffres décimaux.
Elles peuvent être écrites avec ou sans virgule décimale, `.` , ou une partie exponentielle indiquée par « e » ou « e » (après quoi seuls un signe négatif et des chiffres décimaux possibles sont valides).
Les littéraux valides sont les suivants `Double` : `0.0` , `1.2e5` , `1e-5` .

À partir d’une expression de tableau de tout type d’élément, vous pouvez former une `Int` expression à l’aide de la [`Length`](xref:Microsoft.Quantum.Core.Length) fonction intégrée, avec l’expression de tableau placée entre parenthèses.
Par exemple, si `a` est lié à un tableau, `Length(a)` est une expression d’entier.
Si `b` est un tableau de tableaux d’entiers, `Int[][]` , `Length(b)` est le nombre de sous-tableaux dans `b` , et `Length(b[1])` est le nombre d’entiers dans le deuxième sous-tableau de `b` .

À partir de deux expressions numériques du même type, les opérateurs binaires `+` , `-` , `*` et `/` peuvent être utilisés pour former une nouvelle expression numérique.
Le type de la nouvelle expression est le même que les types des expressions constituantes.

À partir de deux expressions entières, utilisez l’opérateur binaire `^` (Power) pour former une nouvelle expression entière.
De même, vous pouvez également utiliser `^` avec deux expressions double pour former une nouvelle expression double.
Enfin, vous pouvez utiliser `^` avec un grand entier à gauche et un entier sur la droite pour former une nouvelle expression d’entier Big.
Dans ce cas, le deuxième paramètre doit être contenu dans 32 bits ; Si ce n’est pas le cas, il déclenche une erreur d’exécution.

À partir de deux expressions entières ou d’entiers Big, forment une nouvelle expression de type entier ou entier Big à l’aide des `%` opérateurs (modulo), (opérateur de bits and), (au niveau du bit or `&&&` `|||` ) ou `^^^` (opérateur de bits XOR).

À partir d’une expression d’entier ou d’entier Big à gauche, et d’une expression d’entier à droite, utilisez les `<<<` opérateurs (décalage arithmétique vers la gauche) ou `>>>` (décalage vers la droite) pour créer une nouvelle expression avec le même type que l’expression de gauche.

Le deuxième paramètre (la valeur de décalage) pour l’opération de décalage doit être supérieur ou égal à zéro ; le comportement des valeurs de décalage négatives n’est pas défini.
La valeur de décalage pour l’opération de décalage doit également tenir dans 32 bits ; Si ce n’est pas le cas, il déclenche une erreur d’exécution.
Si le nombre décalé est un entier, la valeur de décalage est interprétée `mod 64` ; autrement dit, un décalage de 1 et un décalage de 65 ont le même effet.

Pour les valeurs entières et de type entier Big, les décalages sont arithmétiques.
Le décalage d’une valeur négative à gauche ou à droite produit un nombre négatif.
Autrement dit, le décalage d’une étape vers la gauche ou vers la droite est identique à la multiplication ou à la division par 2, respectivement.

Le modulo de la division entière et de l’entier suit le même comportement pour les nombres négatifs que C#. Autrement dit, `a % b` a toujours le même signe que `a` et est `b * (a / b) + a % b` toujours égal à `a` . Par exemple :

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| 5 | 2 | 2 | 1 |
| 5 | -2 | -2 | 1 |
| -5 | 2 | -2 | -1 |
| -5 | -2 | 2 | -1 |

Les opérations de division d’entiers et de modulo fonctionnent de la même façon.

À partir de toute expression numérique, vous pouvez former une nouvelle expression à l’aide de l' `-` opérateur unaire.
La nouvelle expression est du même type que l’expression constitutive.

À partir de toute expression d’entier ou d’entier Big, vous pouvez former une nouvelle expression du même type à l’aide de l' `~~~` opérateur unaire (complément de bits).

## <a name="boolean-expressions"></a>Expressions booléennes

Les deux `Bool` valeurs littérales sont `true` et `false` .

Compte tenu des deux expressions du même type primitif, les `==` `!=` opérateurs binaires et peuvent être utilisés pour construire une `Bool` expression.
L’expression a la valeur true si les deux expressions sont égales et false dans le cas contraire.

Les valeurs des types définis par l’utilisateur ne peuvent pas être comparées, seules leurs valeurs désencapsulées peuvent être comparées. Par exemple, à l’aide de l’opérateur « Unwrap » `!` (expliqué en détail dans les [types dans Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

La comparaison d’égalité pour les `Qubit` valeurs est l’égalité d’identité ; autrement dit, si les deux expressions identifient le même qubit.
Les États des deux qubits ne sont pas comparés, consultés, mesurés ou modifiés par cette comparaison.

La comparaison d’égalité des `Double` valeurs peut être trompeuse en raison des effets arrondis.
Par exemple : `49.0 * (1.0/49.0) != 1.0`.

Compte tenu de deux expressions numériques, les opérateurs binaires `>` , `<` , `>=` et `<=` peuvent être utilisés pour construire une nouvelle expression booléenne qui a la valeur true si la première expression est respectivement supérieure à, inférieure à, supérieure ou égale à, ou inférieure ou égale à la seconde.

Compte tenu de deux expressions booléennes, utilisez l' `and` opérateur binaire pour construire une nouvelle expression booléenne qui a la valeur true si les deux expressions ont la valeur true. De même, l’utilisation `or` de l’opérateur crée une expression qui a la valeur true si l’une des deux expressions a la valeur true.

À partir de toute expression booléenne, l' `not` opérateur unaire peut être utilisé pour construire une nouvelle expression booléenne qui a la valeur true si l’expression constitutive est false.

## <a name="string-expressions"></a>Expressions de chaîne

Q# autorise l’utilisation de chaînes dans l' `fail` instruction (expliquée dans le [Workflow de contrôle](xref:microsoft.quantum.guide.controlflow#fail-statement)) et dans la [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) fonction standard. Le comportement spécifique de ce dernier dépend du simulateur utilisé, mais écrit généralement un message dans la console hôte lorsqu’il est appelé pendant un Q# programme.

Les chaînes dans Q# sont des littéraux ou des chaînes interpolées.

Les littéraux de chaîne sont similaires aux littéraux de chaîne simples dans la plupart des langues : une séquence de caractères Unicode placée entre guillemets doubles `" "` .
À l’intérieur d’une chaîne, utilisez la barre oblique inverse `\` pour échapper un caractère de guillemet double ( `\"` ), ou pour insérer une nouvelle ligne ( `\n` ), un retour chariot ( `\r` ) ou un onglet ( `\t` ).
Par exemple :

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Chaînes interpolées

La Q# syntaxe pour les interpolations de chaînes est un sous-ensemble de la syntaxe C#. Voici les points clés auxquels ils se rapportent Q# :

* Pour identifier un littéral de chaîne comme chaîne interpolée, préfixez-la du symbole `$`. Il ne peut pas y avoir d’espace blanc entre le `$` et le `"` qui démarre un littéral de chaîne.

* L’exemple suivant est un exemple de base [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) qui utilise la fonction pour écrire le résultat d’une mesure dans la console, en même temps que d’autres Q# expressions.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* Toute Q# expression valide peut apparaître dans une chaîne interpolée.

* Les expressions à l’intérieur d’une chaîne interpolée suivent la Q# syntaxe, et non la syntaxe C#. La distinction la plus notable est que Q# ne prend pas en charge les chaînes interpolées textuelles (multiligne).

Pour plus d’informations sur la syntaxe C#, consultez [*chaînes interpolées*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).

## <a name="range-expressions"></a>Expressions de plage

Compte tenu des trois `Int` expressions `start` , `step` et `stop` , l’expression `start .. step .. stop` est une expression de plage dont le premier élément est `start` , le deuxième élément est, le `start+step` troisième élément est `start+step+step` , et ainsi de suite, jusqu’à ce que vous passiez `stop` .
Une plage peut être vide si, par exemple, `step` est positif et `stop < start` .

La plage est comprise entre les deux extrémités. Autrement dit, si la différence entre `start` et `stop` est un entier multiple de `step` , le dernier élément de la plage est `stop` .

Compte tenu des deux `Int` expressions `start` et `stop` , l’expression `start .. stop` est une expression de plage qui est égale à `start .. 1 .. stop` .
Notez que le implicite `step` est + 1 même si `stop` est inférieur à `start` ; dans ce cas, la plage est vide.

Voici quelques exemples de plages :

- `1..3` est la plage 1, 2, 3.
- `2..2..5` est la plage 2, 4.
- `2..2..6` est la plage 2, 4, 6.
- `6..-2..2` est la plage 6, 4, 2.
- `2..1` est la plage vide.
- `2..6..7` est la plage 2.
- `2..2..1` est la plage vide.
- `1..-1..2` est la plage vide.

## <a name="qubit-expressions"></a>Expressions qubit

Les seules `Qubit` expressions sont des symboles liés à `Qubit` des valeurs ou à des éléments de tableau de `Qubit` tableaux.
Il n’existe aucun `Qubit` littéral.

## <a name="pauli-expressions"></a>Expressions Pauli

Les quatre `Pauli` valeurs,,, `PauliI` `PauliX` `PauliY` et `PauliZ` , sont toutes des expressions valides `Pauli` .

À part cela, les seules `Pauli` expressions sont des symboles liés à `Pauli` des valeurs ou à des éléments de tableau de `Pauli` tableaux.

## <a name="result-expressions"></a>Expressions de résultat

Les deux `Result` valeurs, `One` et `Zero` , sont des `Result` expressions valides.

À part cela, les seules `Result` expressions sont des symboles liés à `Result` des valeurs ou à des éléments de tableau de `Result` tableaux.
En particulier, Notez que `One` n’est pas le même que l’entier `1` et qu’il n’y a pas de conversion directe entre eux.
Il en va de même pour `Zero` et `0` .

## <a name="tuple-expressions"></a>Expressions de Tuple

Un littéral de tuple est une séquence d’expressions d’élément du type approprié, séparées par des virgules, placées entre parenthèses.
Par exemple, `(1, One)` est une `(Int, Result)` expression.

À part les littéraux, les seules expressions de tuple sont des symboles liés à des valeurs de tuple, des éléments de tableau de tableaux de tuples et des appels pouvant être appelés qui retournent des tuples.

## <a name="user-defined-type-expressions"></a>Expressions de type User-Defined

Un littéral d’un type défini par l’utilisateur se compose du nom du type suivi d’un littéral de tuple du type de tuple de base du type.
Par exemple, si `IntPair` est un type défini par l’utilisateur basé sur `(Int, Int)` , `IntPair(2, 3)` est un littéral valide de ce type.

À part les littéraux, les seules expressions d’un type défini par l’utilisateur sont les symboles liés aux valeurs de ce type, les éléments de tableau des tableaux de ce type et les appels pouvant être appelés qui retournent ce type.

## <a name="unwrap-expressions"></a>Désencapsuler les expressions

Dans Q# , l’opérateur Unwrap est un point d’exclamation de fin `!` .
Par exemple, si `IntPair` est un type défini par l’utilisateur avec le type sous-jacent `(Int, Int)` et qu' `s` il s’agit d’une variable de valeur `IntPair(2, 3)` , `s!` est `(2, 3)` .

Pour les types définis par l’utilisateur définis en termes d’autres types définis par l’utilisateur, vous pouvez répéter l’opérateur Unwrap. Par exemple, `s!!` indique la valeur doublement désencapsulée de `s` .
Ainsi, si `WrappedPair` est un type défini par l’utilisateur avec le type sous-jacent `IntPair` , et `t` est une variable avec la valeur `WrappedPair(IntPair(1,2))` , `t!!` est alors `(1,2)` .

L' `!` opérateur a une priorité plus élevée que tous les autres opérateurs autres que `[]` pour l’indexation et le découpage de tableau.
`!` et `[]` lient la position. autrement dit, `a[i]![3]` est lu comme `((a[i])!)[3]` : prenez le `i` th élément de `a` , Désencapsulez-le, puis récupérez le troisième élément de la valeur désencapsulée (qui doit être un tableau).

La priorité de l' `!` opérateur a un impact qui peut ne pas être évident.
Si une fonction ou une opération retourne une valeur qui est ensuite désencapsulée, l’appel de fonction ou d’opération doit être mis entre parenthèses afin que le tuple d’argument soit lié à l’appel plutôt qu’à la désencapsulation.
Par exemple :

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expressions de tableau

Un littéral de tableau est une séquence d’une ou plusieurs expressions d’élément, séparées par des virgules, placées entre crochets `[]` .
Tous les éléments doivent être compatibles avec le même type.

À partir de deux tableaux du même type, utilisez l' `+` opérateur binaire pour former un nouveau tableau qui est la concaténation des deux tableaux.
Par exemple : `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Création de tableau

À partir d’un type et d’une `Int` expression, utilisez l' `new` opérateur pour allouer un nouveau tableau de la taille donnée.
Par exemple, `new Int[i + 1]` alloue un nouveau `Int` tableau avec des `i + 1` éléments.

Les littéraux de tableaux vides, tels que `[]` , ne sont pas autorisés.
Au lieu de cela, vous pouvez créer un tableau de longueur égale à zéro à l’aide de `new T[0]` , où `T` est un espace réservé pour un type approprié.

Les éléments d’un nouveau tableau sont initialisés à une valeur par défaut dépendante du type.
Dans la plupart des cas, il s’agit d’une variante de zéro.

Pour qubits et callables, qui sont des références à des entités, il n’existe pas de valeur par défaut raisonnable.
Par conséquent, pour ces types, la valeur par défaut est une référence non valide que vous ne pouvez pas utiliser sans générer d’erreur d’exécution, similaire à une référence null dans des langages tels que C# ou Java.
Les tableaux contenant qubits ou callables doivent être initialisés avec des valeurs autres que celles par défaut avant de pouvoir utiliser leurs éléments en toute sécurité. Pour les routines d’initialisation appropriées, consultez <xref:Microsoft.Quantum.Arrays> .

Les valeurs par défaut pour chaque type sont :

Type | Default
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _qubit non valide_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | La plage vide, `1..1..0`
 `Callable` | _appelable non valide_
 `Array['T]` | `'T[0]`

Les types Tuple initialisent élément par élément.


### <a name="array-elements"></a>Éléments de tableau

À partir d’une expression de tableau et d’une `Int` expression, forment une nouvelle expression à l’aide de l’opérateur d’élément de tableau `[]` .
La nouvelle expression est du même type que le type d’élément du tableau.
Par exemple, si `a` est lié à un tableau de type `Double` , `a[4]` est une `Double` expression.

Si l’expression de tableau n’est pas un identificateur simple, vous devez la placer entre parenthèses pour sélectionner un élément.
Par exemple, si `a` et `b` sont tous deux des tableaux de type `Int` , un élément de la concaténation est exprimé comme suit :

```qsharp
(a + b)[13]
```

Tous les tableaux dans Q# sont de base zéro.
Autrement dit, le premier élément d’un tableau `a` est toujours `a[0]` .


### <a name="array-slices"></a>Tranches de tableau

À partir d’une expression de tableau et d’une `Range` expression, forment une nouvelle expression à l’aide de l’opérateur de tranche de tableau `[ ]` .
La nouvelle expression est du même type que le tableau et contient les éléments de tableau indexés par les éléments de `Range` , dans l’ordre défini par le `Range` .
Par exemple, si `a` est lié à un tableau de type `Double` , `a[3..-1..0]` est une `Double[]` expression qui contient les quatre premiers éléments de, `a` mais dans l’ordre inverse, tels qu’ils apparaissent dans `a` .

Si `Range` est vide, la tranche de tableau résultante a une longueur de zéro.

Tout comme pour le référencement d’éléments de tableau, si l’expression de tableau n’est pas un identificateur simple, vous devez la placer entre parenthèses pour la découper.
Par exemple, si `a` et `b` sont tous deux des tableaux de type `Int` , un segment de la concaténation est exprimé comme suit :

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Valeurs de début/fin déduites

À partir de notre [version 0,8](xref:microsoft.quantum.relnotes), nous prenons en charge les expressions contextuelles pour le découpage de plage. En particulier, vous pouvez omettre les valeurs de début et de fin de plage dans le contexte d’une expression de découpage de plage. Dans ce cas, le compilateur applique les règles suivantes pour déduire les délimiteurs prévus pour la plage :

* Si la valeur de *début* de la plage est omise, la valeur de début déduite
  * est égal à zéro si aucune étape n’est spécifiée ou si l’étape spécifiée est positive.  
  * longueur du tableau découpé moins un si l’étape spécifiée est négative.

* Si la valeur de *fin* de la plage est omise, la valeur de fin déduite
  * longueur du tableau découpé moins un si aucune étape n’est spécifiée ou si l’étape spécifiée est positive.
  * est égal à zéro si l’étape spécifiée est négative.

Quelques exemples :

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a>Expressions de copie et de mise à jour

Étant donné que tous les Q# types sont des types valeur (avec le qubits qui prend un rôle un peu spécial), une « copie » est formellement créée lorsqu’une valeur est liée à un symbole ou lorsqu’un symbole est relié. Autrement dit, le comportement de Q# est le même que si une copie a été créée à l’aide d’un opérateur d’assignation. 

Bien entendu, dans la pratique, seuls les éléments pertinents sont recréés en fonction des besoins. Cela affecte la façon dont vous copiez les tableaux, car il n’est pas possible de mettre à jour les éléments du tableau. La modification d’un tableau existant requiert l’utilisation d’un mécanisme de *copie et de mise à jour* .

Vous pouvez créer un nouveau tableau à partir d’un tableau existant à l’aide d’expressions de *copie et de mise à jour* , qui utilisent les opérateurs `w/` et `<-` .
Une expression de copie et de mise à jour est une expression de la forme `expression1 w/ expression2 <- expression3` , où

* `expression1` doit être `T[]` de type pour un certain type `T` .
* `expression2` définit les index dans le tableau spécifié dans `expression1` à modifier. `expression2` doit être de type `Int` ou `Range` .
* `expression3` valeur (s) utilisée (s) pour mettre à jour les éléments dans `expression1` , en fonction des index spécifiés dans `expression2` . Si `expression2` est `Int` de type, `expression3` doit être de type `T` . Si `expression2` est `Range` de type, `expression3` doit être de type `T[]` .

Par exemple, l’expression copy-and-Update `arr w/ idx <- value` construit un nouveau tableau avec tous les éléments définis sur les éléments correspondants dans `arr` , à l’exception des éléments spécifiés par `idx` , qui est défini sur la ou les valeurs dans `value` . 

Indiqué `arr` contient le tableau `[0,1,2,3]` , puis 

- `arr w/ 0 <- 10` est le tableau `[10,1,2,3]` .
- `arr w/ 2 <- 10` est le tableau `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]` est le tableau `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Expressions de copie et de mise à jour pour les éléments nommés

Des expressions similaires existent pour les éléments nommés dans les types définis par l’utilisateur. 

Par exemple, considérez le type 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Si `c` contient la valeur de type `Complex(1., -1.)` , `c w/ Re <- 0.` est une expression de type qui prend la valeur `Complex` `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Tableaux en escalier

Un tableau en escalier, parfois appelé « tableau de tableaux », est un tableau dont les éléments sont des tableaux.
Les éléments d’un tableau en escalier peuvent être de différentes tailles.
L’exemple suivant montre comment déclarer et initialiser un tableau en escalier représentant une table de multiplication.

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a>Tableaux de callables 

Vous pouvez également créer un tableau de callables.

* Si le type d’élément commun est un type d’opération ou de fonction, tous les éléments doivent avoir les mêmes types d’entrée et de sortie.
* Le type d’élément du tableau prend en charge tous les [functors](xref:microsoft.quantum.guide.operationsfunctions) pris en charge par tous les éléments.
Par exemple, si `Op1` , `Op2` et `Op3` sont tous des `Qubit[] => Unit` opérations, mais `Op1` prend en charge `Adjoint` , `Op2` prend en charge `Controlled` et `Op3` prend en charge les deux :
  * `[Op1, Op2]` est un tableau d' `(Qubit[] => Unit)` opérations.
  * `[Op1, Op3]` est un tableau d' `(Qubit[] => Unit is Adj)` opérations.
  * `[Op2, Op3]` est un tableau d' `(Qubit[] => Unit is Ctl)` opérations.

Toutefois, alors que les opérations `(Qubit[] => Unit is Adj)` et  `(Qubit[] => Unit is Ctl)` ont le type de base commun de `(Qubit[] => Unit)` , les *tableaux* de ces opérations ne partagent pas un type de base commun.

Par exemple, `[[Op1], [Op2]]` génère actuellement une erreur, car elle tente de créer un tableau des deux types de tableau incompatibles `(Qubit[] => Unit is Adj)[]` et `(Qubit[] => Unit is Ctl)[]` .

Pour plus d’informations sur callables, consultez [expressions pouvant être appelées](#callable-expressions) sur cette page ou [opérations Q# et fonctions dans ](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="conditional-expressions"></a>Expressions conditionnelles

À partir de deux expressions du même type et d’une expression booléenne, forment une expression conditionnelle à l’aide du point d’interrogation, de `?` et de la barre verticale `|` . Indiqué `a==b ? c | d` , la valeur de l’expression conditionnelle est `c` si `a==b` a la valeur true et `d` si elle est false.

### <a name="conditional-expressions-with-callables"></a>Expressions conditionnelles avec callables

Les expressions conditionnelles peuvent correspondre à des opérations qui ont les mêmes entrées et sorties, mais prennent en charge différents functors. Dans ce cas, le type de l’expression conditionnelle est une opération avec des entrées et des sorties qui prennent en charge tous les functors pris en charge par les deux expressions.
Par exemple, si `Op1` , `Op2` et `Op3` sont tous des `Qubit[]=>Unit` , mais prend en charge, prend en charge `Op1` `Adjoint` `Op2` `Controlled` et `Op3` prend en charge les deux :

- `flag ? Op1 | Op2` est une `(Qubit[] => Unit)` opération.
- `flag ? Op1 | Op3` est une `(Qubit[] => Unit is Adj)` opération.
- `flag ? Op2 | Op3` est une `(Qubit[] => Unit is Ctl)` opération.

Si l’une des deux expressions de résultat possibles inclut une fonction ou un appel d’opération, cet appel a lieu uniquement si le résultat est celui qui correspond à la valeur de l’appel. Par exemple, dans le cas `a==b ? C(qs) | D(qs)` , si `a==b` a la valeur true, l' `C` opération est appelée, et si elle a la valeur false, seule l' `D` opération est appelée. Cette approche est similaire à *un court-circuit* dans d’autres langages.

## <a name="callable-expressions"></a>Expressions pouvant être appelées

Un littéral pouvant être appelé est le nom d’une opération ou d’une fonction définie dans la portée de compilation. Par exemple, `X` est un littéral d’opération qui fait référence à l’opération de bibliothèque standard `X` , et `Message` est un littéral de fonction qui fait référence à la fonction de bibliothèque standard `Message` .

Si une opération prend en charge `Adjoint` functor, `Adjoint op` est une expression d’opération.
De même, si l’opération prend en charge `Controlled` functor, `Controlled op` est une expression d’opération.
Pour plus d’informations sur les types de ces expressions, consultez [appel des spécialisations d’opérations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Les functors ( `Adjoint` et `Controlled` ) lient plus étroitement que tous les autres opérateurs, à l’exception de l’opérateur Unwrap et de l' `!` indexation de tableau avec `[ ]` .
Par conséquent, les éléments suivants sont tous valides, en supposant que les opérations prennent en charge les functors utilisés :

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Expressions pouvant être appelées par type paramétrable

Vous pouvez utiliser un littéral pouvant être appelé comme valeur, par exemple, pour l’assigner à une variable ou le passer à un autre pouvant être appelé. Dans ce cas, si l’élément pouvant être appelé a des [paramètres de type](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), vous devez fournir les paramètres dans le cadre de la valeur pouvant être appelée.

Une valeur pouvant être appelée ne peut pas avoir de paramètres de type non spécifiés. Par exemple, si `Fun` est une fonction avec la signature `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expressions d’appel pouvant être appelées

À partir d’une expression pouvant être appelée (opération ou fonction) et d’une expression de tuple du type d’entrée de la signature de l’appel, vous pouvez former une *expression* d’appel en ajoutant l’expression de tuple à l’expression pouvant être appelée.
Le type de l’expression d’appel est le type de sortie de la signature de l’appelable.

Par exemple, si `Op` est une opération avec la signature `((Int, Qubit) => Double)` , `Op(3, qubit1)` est une expression de type `Double` .
De même, si `Sin` est une fonction avec la signature `(Double -> Double)` , `Sin(0.1)` est une expression de type `Double` .
Enfin, si `Builder` est une fonction avec la signature `(Int -> (Int -> Int))` , `Builder(3)` est une fonction de `Int` à `Int` .

L’appel du résultat d’une expression de valeur pouvant être appelée nécessite une paire de parenthèses supplémentaires autour de l’expression pouvant être appelée.
Ainsi, pour appeler le résultat de l’appel `Builder` à partir du paragraphe précédent, la syntaxe correcte est la suivante :

```qsharp
(Builder(3))(2)
```

Lors de l’appel d’un pouvant être appelé [par un type paramétrable](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , vous pouvez spécifier les paramètres de type réels entre crochets pointus `< >` après l’expression pouvant être appelée.
Cette action n’est généralement pas nécessaire, car le Q# compilateur déduit les types réels.
Toutefois, elle *est* requise pour une [application partielle](xref:microsoft.quantum.guide.operationsfunctions#partial-application) si un argument de type paramétrable n’est pas spécifié.
Elle est également utile lors du passage d’opérations avec des prises en charge de functor différentes à un pouvant être appelé.

Par exemple, si `Func` a une signature, et possède la signature `('T1, 'T2, 'T1) -> 'T2` et la `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` signature `(Qubit[] => Unit)` , pour appeler en `Func` `Op1` tant que premier argument `Op2` , comme deuxième argument, et `Op3` comme troisième :

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

La spécification de type est requise, car `Op3` et `Op1` ont des types différents, de sorte que le compilateur traite cette opération comme ambiguë sans la spécification.


## <a name="operator-precedence"></a>Priorité des opérateurs

* Tous les opérateurs binaires sont associatifs à droite, à l’exception de `^` .

* Les crochets, `[ ]` , pour le découpage et l’indexation de tableaux, sont liés avant tout opérateur.

* Functors `Adjoint` et `Controlled` Bind après l’indexation de tableau, mais avant tous les autres opérateurs.

* Les parenthèses pour l’appel de l’opération et de la fonction sont également liées avant tout opérateur, mais après l’indexation et les functors du tableau.

Q# opérateurs par ordre de priorité, du plus élevé au plus bas :

Opérateur | Arité | Description | Types d’opérandes
---------|----------|---------|---------------
 fin `!` | Unaire | Désencapsuler | Tout type défini par l’utilisateur
 `-`, `~~~`, `not` | Unaire | Valeur numérique négative, complément au niveau du bit, négation logique | `Int`, `BigInt` ou pour, `Double` ou pour `-` `Int` `BigInt` `~~~` , `Bool` pour `not`
 `^` | Binary | Puissance entière | `Int` ou `BigInt` pour la base, `Int` pour l’exposant
 `/`, `*`, `%` | Binary | Division, multiplication, modulo entier | `Int`, `BigInt` ou `Double` pour `/` et `*` , `Int` ou `BigInt` pour `%`
 `+`, `-` | Binary | Addition ou concaténation de chaînes et de tableaux, soustraction | `Int`, `BigInt` ou `Double` , en plus `String` ou n’importe quel type de tableau pour `+`
 `<<<`, `>>>` | Binary | Décalage vers la gauche, décalage vers la droite | `Int` ou `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | Comparaisons « inférieur à », « inférieur à », « supérieur à », « supérieur à » ou « égal à » | `Int`, `BigInt` ou `Double`
 `==`, `!=` | Binary | comparaisons égales et non égales | tout type primitif
 `&&&` | Binary | ET au niveau du bit | `Int` ou `BigInt`
 `^^^` | Binary | Opération de bits XOR | `Int` ou `BigInt`
 <code>\|\|\|</code> | Binary | Opération de bits OR | `Int` ou `BigInt`
 `and` | Binary | ET logique | `Bool`
 `or` | Binary | OU logique | `Bool`
 `..` | Binaire/ternaire | Opérateur de plage | `Int`
 `?` `|` | Gradient | Logique conditionnelle | `Bool` pour le côté gauche
`w/` `<-` | Gradient | Copier et mettre à jour | Voir les [expressions copy-and-Update](#copy-and-update-expressions)

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous pouvez utiliser des expressions dans Q# , passez à [ Q# opérations et fonctions dans](xref:microsoft.quantum.guide.operationsfunctions) pour apprendre à définir et appeler des opérations et des fonctions.
