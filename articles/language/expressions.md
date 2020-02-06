---
title: Expressions | Microsoft Docs
description: Expressions
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 83fe697aa07a8ab28bd64437c8f5746bc5893b27
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036309"
---
# <a name="expressions"></a>Expressions

## <a name="grouping"></a>Regroupement

À partir de toute expression, cette même expression entre parenthèses est une expression du même type.
Par exemple, `(7)` est une expression `Int`, `([1,2,3])` est une expression de type tableau de `Int`s et `((1,2))` est une expression de type `(Int, Int)`.

L’équivalence entre les valeurs simples et les tuples à un seul élément décrit dans [le modèle de type](xref:microsoft.quantum.language.type-model#tuple-types) supprime l’ambiguïté entre `(6)` en tant que groupe et `(6)` comme un tuple à un seul élément.

## <a name="symbols"></a>Symboles

Le nom d’un symbole lié ou assigné à une valeur de type `'T` est une expression de type `'T`.
Par exemple, si le symbole `count` est lié à la valeur entière `5`, `count` est une expression d’entier.

## <a name="numeric-expressions"></a>Expressions numériques

Les expressions numériques sont des expressions de type `Int`, `BigInt`ou `Double`.
Autrement dit, il s’agit de nombres entiers ou à virgule flottante.

les littéraux de `Int` dans Q # sont identiques aux littéraux C#entiers dans, sauf qu’aucun « l » ou « l » de fin n’est requis (ou autorisé).
Les entiers hexadécimaux et binaires sont pris en charge avec un préfixe « 0x » et « 0b » respectivement.

les littéraux de `BigInt` dans Q # sont identiques aux chaînes d’entiers volumineuses dans .NET, avec un « l » ou « L » de fin.
Les nombres entiers hexadécimaux sont pris en charge avec un préfixe « 0x ».
Par conséquent, les utilisations valides des littéraux de `BigInt` sont les suivantes :

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

les littéraux de `Double` dans Q # sont identiques aux doubles littéraux dans, à ceci près qu’aucun « d » ou « D » de C#fin n’est requis (ou autorisé).

À partir d’une expression de tableau de tout type d’élément, une expression `Int` peut être formée à l’aide de la fonction intégrée `Length`, avec l’expression de tableau placée entre parenthèses, `(` et `)`.
Par exemple, si `a` est lié à un tableau, `Length(a)` est une expression d’entier.
Si `b` est un tableau de tableaux d’entiers, `Int[][]`, `Length(b)` est le nombre de sous-tableaux dans `b`, et `Length(b[1])` est le nombre d’entiers dans le deuxième sous-tableau de `b`.

À partir de deux expressions numériques du même type, les opérateurs binaires `+`, `-`, `*`et `/` peuvent être utilisés pour former une nouvelle expression numérique.
Le type de la nouvelle expression sera le même que les types des expressions constituantes.

À partir de deux expressions entières, l’opérateur binaire `^` (Power) peut être utilisé pour former une nouvelle expression entière.
De même, `^` peut être utilisé avec deux expressions double pour former une nouvelle expression double.
Enfin, `^` peut être utilisé avec un grand entier à gauche et un entier sur la droite pour former une nouvelle expression d’entier Big.
Dans ce cas, le deuxième paramètre doit être contenu dans 32 bits ; Si ce n’est pas le cas, une erreur d’exécution est générée.

À partir de deux expressions entières ou d’entiers Big, une nouvelle expression de type entier ou entier Big peut être formée à l’aide des opérateurs `%` (modulo), `&&&` (and au niveau du bit), `|||` (or au niveau du bit) ou `^^^` (opérateur de bits XOR).

À partir d’une expression d’entier ou d’entier Big à gauche, et d’une expression d’entier à droite, les opérateurs `<<<` (décalage arithmétique vers la gauche) ou `>>>` (décalage vers la droite arithmétique) peuvent être utilisés pour créer une nouvelle expression avec le même type que l’expression de gauche.

Le deuxième paramètre (la valeur de décalage) pour l’opération de décalage doit être supérieur ou égal à zéro ; le comportement des valeurs de décalage négatives n’est pas défini.
La valeur de décalage pour l’opération de décalage doit également tenir dans 32 bits ; Si ce n’est pas le cas, une erreur d’exécution est générée.
Si le nombre à décaler est un entier, la valeur du décalage est interprétée `mod 64`; autrement dit, un décalage de 1 et un décalage de 65 ont le même effet.

Pour les valeurs entières et de type entier Big, les décalages sont arithmétiques.
Si vous déplacez une valeur négative à gauche ou à droite, vous obtenez un nombre négatif.
Autrement dit, le décalage d’une étape vers la gauche ou la droite est exactement identique à la multiplication ou à la division par 2, respectivement.

Le modulo de la division entière et de l’entier suit le même C#comportement pour les nombres négatifs que.
Autrement dit, `a % b` aura toujours le même signe que `a`et `b * (a / b) + a % b` sera toujours égal à `a`.
Par exemple :

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

La Division d’entiers Big et le modulo fonctionnent de la même façon.

Quelle que soit l’expression numérique donnée, une nouvelle expression peut être formée à l’aide de l' `-` opérateur unaire.
La nouvelle expression sera du même type que l’expression constituante.

À partir de toute expression d’entier ou d’entier Big, une nouvelle expression du même type peut être formée à l’aide de l’opérateur unaire `~~~` (complément au niveau du bit).

## <a name="boolean-expressions"></a>Expressions booléennes

Les deux valeurs littérales de `Bool` sont `true` et `false`.

Compte tenu des deux expressions du même type primitif, les opérateurs binaires `==` et `!=` peuvent être utilisés pour construire une expression `Bool`.
L’expression aura la valeur true si les deux expressions sont égales et false dans le cas contraire.

Les valeurs des types définis par l’utilisateur ne peuvent pas être comparées, seules leurs valeurs désencapsulées peuvent être comparées. Par exemple, à l’aide de l’opérateur « désencapsuler » `!` (expliqué dans la [page de modèle Q # type](xref:microsoft.quantum.language.type-model#user-defined-types)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

La comparaison d’égalité pour les valeurs de `Qubit` est l’égalité d’identité ; autrement dit, si les deux expressions identifient le même qubit.
L’état des deux qubits n’est pas comparé, accédé, mesuré ou modifié par cette comparaison.

La comparaison d’égalité pour les valeurs de `Double` peut être trompeuse en raison des effets arrondis.
Par exemple, `49.0 * (1.0/49.0) != 1.0`.

À partir de deux expressions numériques quelconques, les opérateurs binaires `>`, `<`, `>=`et `<=` peuvent être utilisés pour construire une nouvelle expression booléenne qui est true si la première expression est respectivement supérieure à, inférieure à, supérieure ou égale à, ou inférieure ou égale à la seconde.

Compte tenu de deux expressions booléennes, les opérateurs binaires `and` et `or` peuvent être utilisés pour construire une nouvelle expression booléenne qui a la valeur true si les deux expressions (REEE, ou les deux) sont vraies.

À partir de toute expression booléenne, l' `not` opérateur unaire peut être utilisé pour construire une nouvelle expression booléenne qui a la valeur true si l’expression constitutive est false.

## <a name="string-expressions"></a>Expressions de chaîne

Q # permet d’utiliser des chaînes dans l’instruction `fail` et la fonction `Log` standard.

Dans Q #, les chaînes sont des littéraux ou des chaînes interpolées.
Les littéraux de chaîne sont similaires aux littéraux de chaîne simples dans la plupart des langues : une séquence de caractères Unicode placée entre guillemets doubles, `"`.
À l’intérieur d’une chaîne, le caractère de barre oblique inverse `\` peut être utilisé pour échapper un caractère de guillemet double, et pour insérer une nouvelle ligne comme `\n`, un retour chariot comme `\r`et un onglet comme `\t`.
Exemple :

```qsharp
"\"Hello world!\", she said.\n"
```

La syntaxe Q # pour les interpolations de chaînes est un sous C# -ensemble de la syntaxe 7,0 ; Q # ne prend pas en charge les chaînes interpolées textuelles (multiligne).
Consultez [*chaînes interpolées*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) pour la C# syntaxe.

Les expressions à l’intérieur d’une chaîne interpolée suivent la syntaxe C# Q #, et non la syntaxe.
Toute expression Q # valide peut apparaître dans une chaîne interpolée.

## <a name="qubit-expressions"></a>Expressions qubit

Les seules `Qubit` expressions sont des symboles liés aux valeurs `Qubit` ou aux éléments de tableau de `Qubit` tableaux.
Il n’y a aucun littéral de `Qubit`.

## <a name="pauli-expressions"></a>Expressions Pauli

Les quatre valeurs `Pauli`, `PauliI`, `PauliX`, `PauliY`et `PauliZ`, sont toutes des expressions `Pauli` valides.

À part cela, les seules expressions de `Pauli` sont des symboles liés aux valeurs `Pauli` ou aux éléments de tableau de `Pauli` tableaux.

## <a name="result-expressions"></a>Expressions de résultat

Les deux valeurs `Result`, `One` et `Zero`, sont des expressions `Result` valides.

À part cela, les seules expressions de `Result` sont des symboles liés aux valeurs `Result` ou aux éléments de tableau de `Result` tableaux.
En particulier, Notez que `One` n’est pas le même que l’entier `1`et qu’il n’y a pas de conversion directe entre eux.
Il en va de même pour `Zero` et `0`.

## <a name="range-expressions"></a>Expressions de plage

Compte tenu des trois expressions de `Int` `start`, `step`et `stop`, `start .. step .. stop` est une expression de plage dont le premier élément est `start`, le deuxième élément est `start+step`, le troisième élément est `start+step+step`, etc., jusqu’à ce que `stop` soit passé.
Une plage peut être vide si, par exemple, `step` est positif et `stop < start`.
Le dernier élément de la plage sera `stop` si la différence entre `start` et `stop` est un multiple entier de `step`; autrement dit, la plage est incluse aux deux extrémités.

Compte tenu des deux `Int` expressions `start` et `stop`, `start .. stop` est une expression de plage qui est égale à `start .. 1 .. stop`.
Notez que le `step` implicite est + 1 même si `stop` est inférieur à `start`; dans ce cas, la plage est vide.

Voici quelques exemples de plages :

- `1..3` est la plage 1, 2, 3.
- `2..2..5` est la plage 2, 4.
- `2..2..6` est la plage 2, 4, 6.
- `6..-2..2` est la plage 6, 4, 2.
- `2..1` est la plage vide.
- `2..6..7` est la plage 2.
- `2..2..1` est la plage vide.
- `1..-1..2` est la plage vide.

## <a name="callable-expressions"></a>Expressions pouvant être appelées

Un littéral pouvant être appelé est le nom d’une opération ou d’une fonction définie dans la portée de compilation.
Par exemple, `X` est un littéral d’opération qui fait référence à l’opération de `X` de la bibliothèque standard, et `Message` est un littéral de fonction qui fait référence à la fonction de `Message` de la bibliothèque standard.

Si une opération prend en charge l' `Adjoint` functor, `Adjoint op` est une expression d’opération.
De même, si l’opération prend en charge l' `Controlled` functor, `Controlled op` est une expression d’opération.
Les types de ces expressions sont spécifiés dans les [functors](xref:microsoft.quantum.language.type-model#functors).

Les functors (`Adjoint` et `Controlled`) se lient plus étroitement que tous les autres opérateurs, à l’exception de l’opérateur Unwrap `!` et de l’indexation de tableau avec `[]`.
Par conséquent, les éléments suivants sont tous valides, en supposant que les opérations prennent en charge les functors utilisés :

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

Un littéral pouvant être appelé peut être utilisé comme valeur, par exemple pour assigner à une variable ou pour passer à un autre pouvant être appelé.
Dans ce cas, si l’appelable possède des paramètres de type, ceux-ci doivent être fournis dans le cadre de la valeur pouvant être appelée.
Une valeur pouvant être appelée ne peut pas avoir de paramètres de type non spécifiés.

Par exemple, si `Fun` est une fonction avec la signature `'T1->Unit`:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expressions d’appel pouvant être appelées

À partir d’une expression (opération ou fonction) pouvant être appelée et d’une expression de tuple du type d’entrée de la signature de l’appel, une expression d’appel peut être formée en ajoutant l’expression de tuple à l’expression pouvant être appelée.
Le type de l’expression d’appel est le type de sortie de la signature de l’appelable.

Par exemple, si `Op` est une opération avec la signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` est une expression de type `Double`.
De même, si `Sin` est une fonction avec la signature `(Double -> Double)`, `Sin(0.1)` est une expression de type `Double`.
Enfin, si `Builder` est une fonction avec la signature `(Int -> (Int -> Int))`, `Builder(3)` est une fonction de into en int.

L’appel du résultat d’une expression de valeur pouvant être appelée nécessite une paire de parenthèses supplémentaires autour de l’expression pouvant être appelée.
Ainsi, pour appeler le résultat de l’appel de `Builder` à partir du paragraphe précédent, la syntaxe correcte est la suivante :

```qsharp
(Builder(3))(2)
```

Lors de l’appel d’un pouvant être appelé par un type paramétrable, les paramètres de type réels peuvent être spécifiés entre crochets `<` et `>` après l’expression pouvant être appelée.
Cela n’est généralement pas nécessaire, car le compilateur Q # déduira les types réels.
Elle est requise pour une application partielle (voir ci-dessous) si un argument de type paramétrable n’est pas spécifié.
Elle est également parfois utile lors du passage d’opérations avec des prises en charge de functor différentes à un pouvant être appelé.

Par exemple, si `Func` possède la signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` et `Op2` possèdent la signature `(Qubit[] => Unit is Adj)`, et `Op3` a une signature `(Qubit[] => Unit)`, pour appeler `Func` avec `Op1` comme premier argument, `Op2` comme deuxième, et `Op3` comme troisième argument :

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

La spécification de type est requise, car `Op3` et `Op1` ont des types différents, de sorte que le compilateur traite cette opération comme ambiguë sans la spécification.

### <a name="partial-application"></a>Application partielle

En fonction d’une expression pouvant être appelée, un nouvel appelable peut être créé en fournissant un sous-ensemble des arguments à l’appelable.
C’est ce que l’on appelle une _application partielle_.

Dans Q #, un appelable partiellement appliqué est exprimé en écrivant une expression d’appel normale, mais en utilisant un trait de soulignement, `_`pour les arguments non spécifiés.
L’appelable résultant a le même type de résultat que l’appel de base, et les mêmes spécialisations pour les opérations.
Le type d’entrée de l’application partielle est simplement le type d’origine avec les arguments spécifiés supprimés.

Si une variable mutable est passée comme argument spécifié lors de la création d’une application partielle, la valeur actuelle de la variable est utilisée.
La modification de la valeur de la variable par la suite n’aura pas d’impact sur l’application partielle.

Par exemple, si `Op` a le type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))` a le type `(((Qubit,Qubit), Double) => Unit is Adj)`, et a donc `Op(5,_)`.
- `Op(_,(_,1.0))` a le type `((Int, (Qubit,Qubit)) => Unit is Adj)`.
- `Op(_,((q1,q2),_))` a le type `((Int,Double) => Unit is Adj)`.
   Notez que nous avons appliqué ici une équivalence de tuple de Singleton.

Si l’appelable partiellement appliqué a des paramètres de type qui ne peuvent pas être déduits par le compilateur, ils doivent être fournis au niveau du site d’appel.
L’application partielle ne peut pas avoir de paramètres de type non spécifiés.

Par exemple, si `Op` a le type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>Récursivité

Q # callables peuvent être récursives directement ou indirectement.
Autrement dit, une opération ou une fonction peut s’appeler elle-même, ou elle peut appeler un autre pouvant être appelé, qui appelle directement ou indirectement l’opération pouvant être appelée.

Il existe toutefois deux commentaires importants sur l’utilisation de la récursivité :

- L’utilisation de la récursivité dans les opérations est susceptible d’interférer avec certaines optimisations.
  Cela peut avoir un impact important sur la durée d’exécution de l’algorithme.
- En cas d’exécution sur un appareil Quantum réel, l’espace de pile peut être limité et, par conséquent, une récurrence profonde peut entraîner une erreur d’exécution.
  En particulier, le compilateur et le runtime Q # n’identifient pas et n’optimisent pas la récurrence de la fin.

## <a name="tuple-expressions"></a>Expressions de Tuple

Un littéral de tuple est une séquence d’expressions d’élément du type approprié, séparées par des virgules, placées entre `(` et `)`.
Par exemple, `(1, One)` est une expression `(Int, Result)`.

À part les littéraux, les seules expressions de tuple sont des symboles liés à des valeurs de tuple, des éléments de tableau de tableaux de tuples et des appels pouvant être appelés qui retournent des tuples.

## <a name="user-defined-type-expressions"></a>Expressions de type défini par l’utilisateur

Un littéral d’un type défini par l’utilisateur se compose du nom du type suivi d’un littéral de tuple du type de tuple de base du type.
Par exemple, si `IntPair` est un type défini par l’utilisateur basé sur `(Int, Int)`, `IntPair(2,3)` serait un littéral valide de ce type.

À part les littéraux, les seules expressions d’un type défini par l’utilisateur sont les symboles liés aux valeurs de ce type, les éléments de tableau des tableaux de ce type et les appels pouvant être appelés qui retournent ce type.

## <a name="unwrap-expressions"></a>Désencapsuler les expressions

Dans Q #, l’opérateur Unwrap est un point d’exclamation de fin `!`.
Par exemple, si `IntPair` est un type défini par l’utilisateur avec le type sous-jacent `(Int, Int)`et `s` était une variable avec une valeur `IntPair(2,3)`, `s!` serait `(2,3)`.

Pour les types définis par l’utilisateur définis en termes d’autres types définis par l’utilisateur. l’opérateur Unwrap peut être répété ; par exemple, `s!!` indique la valeur doublement désencapsulée de `s`.
Par conséquent, si `WrappedPair` est un type défini par l’utilisateur avec le type sous-jacent `IntPair`et `t` est une variable avec une valeur `WrappedPair(IntPair(1,2))`, `t!!` est `(1,2)`.

L’opérateur `!` a une priorité plus élevée que tous les autres opérateurs autres que `[]` pour l’indexation et le découpage de tableau.
`!` et `[]` lier la position ; autrement dit, `a[i]![3]` doit être lu comme `((a[i])!)[3]`: prenez le `i`'ième élément de `a`, Désencapsulez-le, puis récupérez le troisième élément de la valeur désencapsulée (qui doit être un tableau).

La priorité de l’opérateur `!` a un impact qui peut ne pas être évident.
Si une fonction ou une opération retourne une valeur qui est ensuite désencapsulée, l’appel de fonction ou d’opération doit être mis entre parenthèses afin que le tuple d’argument soit lié à l’appel plutôt qu’à la désencapsulation.
Par exemple :

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expressions de tableau

Un littéral de tableau est une séquence d’une ou plusieurs expressions d’élément, séparées par des virgules, placées entre `[` et `]`.
Tous les éléments doivent être compatibles avec le même type.

Si le type d’élément commun est un type d’opération ou de fonction, tous les éléments doivent avoir les mêmes types d’entrée et de sortie.
Le type d’élément du tableau prend en charge tous les functors pris en charge par tous les éléments.
Par exemple, si `Op1`, `Op2`et `Op3` tous sont `Qubit[] => Unit`, mais `Op1` prend en charge `Adjoint`, `Op2` prend en charge `Controlled`, et `Op3` prend en charge les deux éléments suivants :

- `[Op1, Op2]` est un tableau d’opérations de `(Qubit[] => Unit)`.
- `[Op1, Op3]` est un tableau d’opérations de `(Qubit[] => Unit is Adj)`.
- `[Op2, Op3]` est un tableau d’opérations de `(Qubit[] => Unit is Ctl)`.

Les littéraux de tableaux vides, `[]`, ne sont pas autorisés.
À la place, à l’aide de `new ★[0]`, où `★` est l’espace réservé pour un type approprié, permet de créer le tableau de longueur zéro souhaité.

À partir de deux tableaux du même type, l’opérateur `+` binaire peut être utilisé pour former un nouveau tableau qui est la concaténation des deux tableaux.
Par exemple, `[1,2,3] + [4,5,6]` est `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Création de tableau

À partir d’un type et d’une expression `Int`, l’opérateur `new` peut être utilisé pour allouer un nouveau tableau de la taille donnée.
Par exemple, `new Int[i+1]` allouerait un nouveau tableau `Int` avec des éléments `i+1`.

Les éléments d’un nouveau tableau sont initialisés à une valeur par défaut dépendante du type.
Dans la plupart des cas, il s’agit d’une variante de zéro.

Pour qubits et callables, qui sont des références à des entités, il n’existe pas de valeur par défaut raisonnable.
Par conséquent, pour ces types, la valeur par défaut est une référence non valide qui ne peut pas être utilisée sans générer d’erreur d’exécution.
Cela est similaire à une référence null dans des langages C# tels que ou Java.
Les tableaux contenant qubits ou callables doivent être correctement initialisés avec des valeurs autres que celles par défaut avant que leurs éléments puissent être utilisés en toute sécurité. Les routines d’initialisation appropriées se trouvent dans <xref:microsoft.quantum.arrays>.

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
 `Range` | Plage vide, `1..1..0`
 `Callable` | _appelable non valide_
 `Array['T]` | `'T[0]`

Les types Tuple sont initialisés élément par élément.


### <a name="jagged-arrays"></a>Tableaux en escalier

Un tableau en escalier, parfois appelé « tableau de tableaux », est un tableau dont les éléments sont des tableaux. Les éléments d’un tableau en escalier peuvent être de différentes tailles. L’exemple suivant montre comment déclarer et initialiser un tableau en escalier représentant une table de multiplication.

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


### <a name="array-slices"></a>Tranches de tableau

À partir d’une expression de tableau et d’une expression de `Range`, une nouvelle expression peut être formée à l’aide de la `[` et `]` opérateur de tranche de tableau.
La nouvelle expression est du même type que le tableau et contient les éléments de tableau indexés par les éléments de l' `Range`, dans l’ordre défini par le `Range`.
Par exemple, si `a` est lié à un tableau de `Double`s, `a[3..-1..0]` est une expression `Double[]` qui contient les quatre premiers éléments de `a`, mais dans l’ordre inverse tel qu’ils apparaissent dans `a`.

Si le `Range` est vide, la tranche de tableau résultante aura une longueur égale à zéro.

Si l’expression de tableau n’est pas un identificateur simple, elle doit être placée entre parenthèses afin de la découper.
Par exemple, si `a` et `b` sont deux tableaux de `Int`, un segment de la concaténation est exprimé comme suit :

```qsharp
(a+b)[1..2..7]
```

Tous les tableaux dans Q # sont de base zéro.
Autrement dit, le premier élément d’un tableau `a` est toujours `a[0]`.

À partir de notre version 0,8, nous prenons en charge les expressions contextuelles pour le découpage de plage. En particulier, les valeurs de début et de fin de plage peuvent être omises dans le contexte d’une expression de découpage de plage. Dans ce cas, le compilateur applique les règles suivantes pour déduire les délimiteurs prévus pour la plage. 

Par exemple, si la valeur de début de la plage est omise, la valeur de début déduite 
- est égal à zéro si aucune étape n’est spécifiée ou si l’étape spécifiée est positive, et 
- longueur du tableau découpé moins un si l’étape spécifiée est négative. 

Si la valeur de fin de la plage est omise, la valeur de fin déduite 
- est la longueur du tableau découpé moins un si aucune étape n’est spécifiée ou si l’étape spécifiée est positive, et 
- est égal à zéro si l’étape spécifiée est négative. 

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

## <a name="array-element-expressions"></a>Expressions d’élément de tableau

À partir d’une expression de tableau et d’une expression de `Int`, une nouvelle expression peut être formée à l’aide du `[` et de `]` opérateur d’élément de tableau.
La nouvelle expression sera du même type que le type d’élément du tableau.
Par exemple, si `a` est lié à un tableau de `Double`s, `a[4]` est une expression `Double`.

Si l’expression de tableau n’est pas un identificateur simple, elle doit être placée entre parenthèses pour pouvoir sélectionner un élément.
Par exemple, si `a` et `b` sont deux tableaux de `Int`, un élément de la concaténation est exprimé comme suit :

```qsharp
(a+b)[13]
```

Tous les tableaux dans Q # sont de base zéro.
Autrement dit, le premier élément d’un tableau `a` est toujours `a[0]`.


## <a name="copy-and-update-expressions"></a>Expressions de copie et de mise à jour

Vous pouvez créer des tableaux à partir d’expressions existantes à l’aide d’expressions de copie et de mise à jour.
Une expression de copie et de mise à jour est une expression de la forme `expression1 w/ expression2 <- expression3`, où `expression1` doit être de type `T[]` pour un `T`de type. La deuxième `expression2` définit les index des éléments à modifier comparés au tableau dans `expression1` et doit être de type `Int` ou de type `Range`... Si `expression2` est de type `Int`, `expression3` doit être de type `T`. Si `expression2` est de type `Range`, `expression3` doit être de type `T[]`.

Une expression copy-and-Update `arr w/ idx <- value` construit un nouveau tableau avec tous les éléments définis sur l’élément correspondant dans `arr`, à l’exception des éléments situés à `idx`, qui sont définis sur le ou les deux dans `value`. Par exemple, si `arr` contient un tableau `[0,1,2,3]`, alors 
- `arr w/ 0 <- 10` est le tableau `[10,1,2,3]`.
- `arr w/ 2 <- 10` est le tableau `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]` est le tableau `[10,1,12,3]`.

Des expressions similaires existent pour les éléments nommés dans les types définis par l’utilisateur. Prenons l’exemple du type 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Si `c` contient la valeur de type `Complex(1.,-1.)`, `c w/ Re <- 0.` est une expression de type `Complex` qui prend la valeur `Complex(0.,-1.)`.

## <a name="conditional-expressions"></a>Expressions conditionnelles

À partir de deux autres expressions du même type et d’une expression booléenne, l’expression conditionnelle peut être formée à l’aide du point d’interrogation `?` et de la barre verticale `|`.
Par exemple, `a==b ? c | d`.
Dans cet exemple, la valeur de l’expression conditionnelle est `c` si `a==b` a la valeur true et `d` si la valeur est false.

Les deux expressions peuvent être évaluées à des opérations qui ont les mêmes entrées et sorties, mais prennent en charge différents functors.
Dans ce cas, le type de l’expression conditionnelle est une opération avec les entrées et sorties qui prend en charge tous les functors pris en charge par les deux expressions.
Par exemple, si `Op1`, `Op2`et `Op3` tous sont `Qubit[]=>Unit`, mais `Op1` prend en charge `Adjoint`, `Op2` prend en charge `Controlled`, et `Op3` prend en charge les deux éléments suivants :

- `flag ? Op1 | Op2` est une opération de `(Qubit[] => Unit)`.
- `flag ? Op1 | Op3` est une opération de `(Qubit[] => Unit is Adj)`.
- `flag ? Op2 | Op3` est une opération de `(Qubit[] => Unit is Ctl)`.

Si l’une des deux expressions de résultat possibles inclut une fonction ou un appel d’opération, cet appel aura lieu uniquement si ce résultat est celui qui sera la valeur de l’appel.
Par exemple, dans le cas `a==b ? C(qs) | D(qs)`, si `a==b` a la valeur true, l’opération `C` sera appelée, et si elle a la valeur false, seule `D` sera appelée.
Cela est similaire au court-circuit dans d’autres langages.


## <a name="operator-precedence"></a>Priorité des opérateurs

Tous les opérateurs binaires sont associatifs à droite, à l’exception de `^`.

Des crochets, des `[` et des `]`, pour la découpage et l’indexation de tableaux, liez avant un opérateur.

Les functors `Adjoint` et `Controlled` liés après l’indexation de tableau, mais avant tous les autres opérateurs.

Les parenthèses pour l’appel de l’opération et de la fonction sont également liées avant tout opérateur, mais après l’indexation et les functors du tableau.

Opérateurs par ordre de priorité, du plus élevé au plus bas :

Opérateur | Arité | Description | Types d’opérandes
---------|----------|---------|---------------
 `!` de fin | Unaire | Unwrap (Désencapsuler) | Tout type défini par l’utilisateur
 `-`, `~~~`, `not` | Unaire | Valeur numérique négative, complément au niveau du bit, négation logique | `Int`, `BigInt` ou `Double` pour `-`, `Int` ou `BigInt` pour `~~~`, `Bool` pour `not`
 `^` | Binary | Puissance entière | `Int` ou `BigInt` pour la base, `Int` pour l’exposant
 `/`, `*`, `%` | Binary | Division, multiplication, modulo entier | `Int`, `BigInt` ou `Double` pour `/` et `*`, `Int` ou `BigInt` pour `%`
 `+`, `-` | Binary | Addition ou concaténation de chaînes et de tableaux, soustraction | `Int`, `BigInt` ou `Double`, en plus `String` ou n’importe quel type de tableau pour `+`
 `<<<`, `>>>` | Binary | Décalage vers la gauche, décalage vers la droite | `Int` ou `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | Comparaisons « inférieur à », « inférieur à », « supérieur à », « supérieur à » ou « égal à » | `Int`, `BigInt` ou `Double`
 `==`, `!=` | Binary | comparaisons égales et non égales | tout type primitif
 `&&&` | Binary | ET au niveau du bit | `Int` ou `BigInt`
 `^^^` | Binary | Opération de bits XOR | `Int` ou `BigInt`
 <code>\|\|\|</code> | Binary | Opération de bits OR | `Int` ou `BigInt`
 `and` | Binary | ET logique | `Bool`
 `or` | Binary | OU logique | `Bool`
 `..` | Binaire/ternaire | Opérateur de plage | `Int`
 `?` `|` | Gradient | Logique conditionnelle | `Bool` pour la partie gauche
`w/` `<-` | Gradient | Copier et mettre à jour | Voir les [expressions copy-and-Update](#copy-and-update-expressions)
