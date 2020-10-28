---
title: Types dans Q#
description: En savoir plus sur les différents types utilisés dans le Q# langage de programmation.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691614"
---
# <a name="types-in-no-locq"></a>Types dans Q#

Cet article décrit le Q# modèle de type et la syntaxe permettant de spécifier et d’utiliser des types. Pour plus d’informations sur la création et l’utilisation d’expressions de ces types, consultez [expressions de type](xref:microsoft.quantum.guide.expressions).

Nous constatons que Q# est un langage *fortement typé* , de sorte que l’utilisation prudente de ces types peut aider le compilateur à fournir des garanties fortes sur les Q# programmes au moment de la compilation.
Pour fournir les garanties les plus fortes possibles, les conversions entre Q# les types dans doivent être explicites à l’aide d’appels à des fonctions qui expriment cette conversion. 
Q# fournit une variété de ces fonctions dans le cadre de l' <xref:Microsoft.Quantum.Convert> espace de noms.
Les casts en types compatibles, en revanche, se produisent implicitement. 

Q# fournit les deux types primitifs, qui sont utilisés directement, et diverses façons de produire de nouveaux types à partir d’autres types.
Nous décrivons chacun d’entre eux dans le reste de cet article.

## <a name="primitive-types"></a>Types primitifs

Le Q# langage fournit les *types primitifs* suivants, que vous pouvez utiliser directement dans les Q# programmes. Vous pouvez également utiliser ces types primitifs pour construire de nouveaux types.

- Le `Int` type représente un entier signé 64 bits, par exemple,, `2` , `107` `-5` .
- Le `BigInt` type représente un entier signé de taille arbitraire, par exemple,,, `2L` `107L` `-5L` .
   Ce type est basé sur .NET <xref:System.Numerics.BigInteger>
   entrer.

- Le `Double` type représente un nombre à virgule flottante double précision, par exemple,,, `0.0` `-1.3` `4e-7` .
- Le `Bool` type représente une valeur booléenne de `true` ou `false` .
- Le `Range` type représente une séquence d’entiers, dénotée par `start..step..stop` , où le signalement de l’étape est facultatif. 
   Par exemple, `start .. stop` correspond à `start..1..stop` , et `1..2..7` représente la séquence $ \{ 1, 3, 5, 7 \} $.
- Le `String` type est une séquence de caractères Unicode qui est opaque pour l’utilisateur une fois créé.
  Utilisez le `string` type pour signaler des messages à un hôte classique dans le cas d’une erreur ou d’un événement de diagnostic.
- Le `Unit` type ne peut avoir qu’une seule valeur, `()` . 
  Utilisez ce type pour indiquer qu’une Q# fonction ou une opération ne retourne aucune information. 
- Le `Qubit` type représente un bit Quantum ou qubit.
   `Qubit`les s sont opaques à l’utilisateur. La seule opération possible avec eux, à l’exception de leur passage à une autre opération, consiste à tester l’identité (égalité).
   Enfin, vous implémentez des actions sur `Qubit` s en appelant des instructions intrinsèques sur un processeur Quantum (ou un simulateur Quantum).
- Le `Pauli` type représente l’un des quatre opérateurs Pauli à qubit unique.
   Utilisez ce type pour désigner l’opération de base pour les rotations et pour spécifier l’observable mesuré.
   Il s’agit d’un type énuméré qui a quatre valeurs possibles : `PauliI` , `PauliX` , `PauliY` et `PauliZ` , qui sont des constantes de type `Pauli` .
- Le `Result` type représente le résultat d’une mesure.
   Il s’agit d’un type énuméré avec deux valeurs possibles : `One` et `Zero` , qui sont des constantes de type `Result` .
   `Zero` indique que le eigenvalue + 1 a été mesuré ; `One` indique que le eigenvalue-1 a été mesuré.

Les constantes,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` et `Zero` sont tous des symboles réservés dans Q# .

## <a name="array-types"></a>Types de tableaux

* Pour tout Q# type valide, il existe un type qui représente un tableau de valeurs de ce type.
    Par exemple, `Qubit[]` et `(Bool, Pauli)[]` représentent des tableaux de `Qubit` valeurs et de `(Bool, Pauli)` valeurs de Tuple.

* Un tableau de tableaux est également valide. En développant l’exemple précédent, un tableau de `(Bool, Pauli)` tableaux est indiqué `(Bool, Pauli)[][]` .

> [!NOTE] 
> Cet exemple, `(Bool, Pauli)[][]` , représente un tableau potentiellement irrégulier de tableaux et non un tableau rectangulaire à deux dimensions. Q# ne prend pas en charge les tableaux multidimensionnels rectangulaires.

* Une valeur de tableau peut être écrite dans Q# le code source à l’aide de crochets autour des éléments d’un tableau, comme dans `[PauliI, PauliX, PauliY, PauliZ]` .
Le type de base commun de tous les éléments du tableau détermine le type d’un littéral de tableau. Par conséquent, la construction d’un tableau avec des éléments qui n’ont pas de type de base commun génère une erreur.  
Pour obtenir un exemple, consultez [tableaux de callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).

    > [!WARNING]
    > Une fois créés, les éléments d’un tableau ne peuvent pas être modifiés.
    > Pour construire un tableau modifié, utilisez les [instructions Update-and-réassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) ou les [expressions copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).

* Un tableau peut également être créé à partir de sa taille à l’aide du `new` mot clé :

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* Utilisez la fonction principale `Length` pour obtenir le nombre d’éléments d’un tableau sous la forme d’un `Int` .
* Les tableaux peuvent être en indice pour obtenir des éléments uniques ou de nouveaux tableaux contenant un sous-ensemble des éléments d’un tableau.
Les indices de tableaux sont de base zéro et doivent être de type `Int` ou de type `Range` :

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>Types de tuples

Les tuples sont un concept puissant utilisé dans l’ensemble Q# pour collecter des valeurs dans une valeur unique, ce qui facilite leur transmission.
En particulier, en utilisant la notation de tuple, vous pouvez exprimer que chaque opération et pouvant être appelée accepte exactement une entrée et retourne une seule sortie.

* À partir de zéro, un ou plusieurs types différents `T0` , `T1` ,..., `Tn` , vous pouvez désigner un nouveau  *type de tuple* comme `(T0, T1, ..., Tn)` .
Les types utilisés pour construire un nouveau type de tuple peuvent eux-mêmes être des tuples, comme dans `(Int, (Qubit, Qubit))` .
Toutefois, cette imbrication est toujours finie, car les types de tuple ne peuvent en aucun cas contenir eux-mêmes.

* Les valeurs du nouveau type de tuple sont des tuples formés par des séquences de valeurs de chaque type dans le tuple.
Par exemple, `(3, false)` est un tuple dont le type est le type de Tuple `(Int, Bool)` .
Il est possible de créer des tableaux de tuples, des tuples de tableaux, des tuples de sous-tuples, etc.

* À partir de Q# 0,3, `Unit` est le nom du *type* du tuple vide ; `()` est utilisé pour la *valeur* du tuple vide.

* Les instances de tuple sont immuables.
Q# ne fournit pas de mécanisme permettant de modifier le contenu d’un tuple une fois créé.



### <a name="singleton-tuple-equivalence"></a>Équivalence de tuple de Singleton

Il est possible de créer un tuple (élément unique) Singleton `('T1)` , tel que `(5)` ou `([1,2,3])` .
Toutefois, Q# traite un tuple Singleton comme équivalant à une valeur du type délimité.
Autrement dit, il n’existe aucune différence entre `5` et `(5)` , ou entre et `5` `(((5)))` , ou entre `(5, (6))` et `(5, 6)` .
Il est tout aussi valide que d’écrire, `(5)+3` car `5+3` les deux expressions ont la valeur `8` .

Cette équivalence s’applique à tous les usages, y compris les affectations et les expressions.
À partir de toute expression, cette même expression entre parenthèses est une expression du même type.
Par exemple, `(7)` est une expression de type `Int` , `([1,2,3])` est une expression de type `Int[]` et `((1,2))` est une expression de type `(Int, Int)` .

En particulier, cela signifie que vous pouvez afficher une opération ou une fonction dont le type de tuple d’entrée ou de sortie a un champ comme prenant un argument unique ou en retournant une valeur unique.

Nous faisons référence à cette propriété en tant qu' _équivalence de tuples Singleton_ .


## <a name="user-defined-types"></a>Types définis par l'utilisateur

Une déclaration de type défini par l’utilisateur se compose du mot clé `newtype` , suivi du nom du type défini par l’utilisateur, d’un `=` , d’une spécification de type valide et d’un point-virgule de fin.

Par exemple :

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* Chaque Q# fichier source peut déclarer un nombre quelconque de types définis par l’utilisateur.
* Les noms de types doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms d’opération et de fonction.
* Les types définis par l’utilisateur sont distincts, même si les types de base sont identiques.
En particulier, il n’y a pas de conversion automatique entre les valeurs de deux types définis par l’utilisateur, même si les types sous-jacents sont identiques.

### <a name="named-vs-anonymous-items"></a>Éléments nommés et anonymes

Un Q# fichier peut définir un nouveau type nommé contenant une valeur unique de n’importe quel type légal.
Pour tout type de Tuple `T` , vous pouvez déclarer un nouveau type défini par l’utilisateur qui est un sous-type de `T` avec l' `newtype` instruction.
Dans l' @"microsoft.quantum.math" espace de noms, par exemple, les nombres complexes sont définis comme un type défini par l’utilisateur :

```qsharp
newtype Complex = (Double, Double);
```
Cette instruction crée un nouveau type avec deux éléments anonymes de type `Double` .   

Outre les éléments anonymes, les types définis par l’utilisateur prennent également en charge les *éléments nommés* à la Q# version 0,7 ou une version ultérieure. Par exemple, vous pouvez nommer les éléments en `Real` pour le double représentant la partie réelle d’un nombre complexe et `Imag` pour la partie imaginaire : 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
L’attribution d’un nom à un élément dans un type défini par l’utilisateur n’implique pas que tous les éléments doivent être nommés-toute combinaison d’éléments nommés et sans nom est prise en charge. En outre, les éléments internes peuvent également être nommés.
Le type `Nested` , tel que défini ci-dessous, a un type sous-jacent `(Double, (Int, String))` dont seul l’élément de type `Int` est nommé et tous les autres éléments sont anonymes. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Les éléments nommés présentent l’avantage de pouvoir accéder directement à l’aide de l' *opérateur d’accès* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

En plus de fournir des alias courts pour les types de tuple potentiellement compliqués, un avantage significatif de la définition de ces types est qu’ils peuvent documenter l’intention d’une valeur particulière.
En revenant à l’exemple de `Complex` , il est possible de définir une coordonnée polaire représentation comme type défini par l’utilisateur :

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

Même si `Complex` et `ComplexPolar` les deux ont un type sous-jacent `(Double, Double)` , les deux types sont entièrement incompatibles dans, ce qui Q# réduit le risque d’appeler accidentellement une fonction mathématique complexe avec des coordonnées polaires, et vice versa.

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Accéder aux éléments anonymes avec l’opérateur Unwrap

Pour accéder aux éléments anonymes, commencez par extraire la valeur encapsulée à l’aide de l’opérateur postfix `!` .
Avec l’opérateur « Unwrap », `!` , vous pouvez extraire la valeur contenue dans un type défini par l’utilisateur.
Le type d’une telle expression « Unwrap » est le type sous-jacent du type défini par l’utilisateur. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Un opérateur Unwrap unique désencapsule une couche de renvoi à la ligne. Utilisez plusieurs opérateurs de désencapsulage pour accéder à une valeur encapsuleuse.

Par exemple :

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

Pour plus d’informations sur l’opérateur Unwrap, consultez [expressions de Q# type dans ](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Création de valeurs de types définis par l’utilisateur

Créez les valeurs d’un type défini par l’utilisateur en appelant le constructeur de type correspondant :

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Vous pouvez également créer de nouvelles valeurs à partir de valeurs existantes à l’aide d' [expressions de copie et de mise à jour](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Tout comme c’est le cas avec les tableaux, les expressions copy-and-Update copient toutes les valeurs d’élément de l’expression d’origine, à l’exception des éléments nommés spécifiés. Pour ces exceptions, les valeurs de ces éléments sont les valeurs définies sur le côté droit de l’expression. Toutes les autres constructions de langage disponibles pour les éléments de tableau, par exemple les [instructions Update-and-réassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), existent pour les éléments nommés dans les types définis par l’utilisateur.

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

* Vous pouvez utiliser des types définis par l’utilisateur partout où vous utilisez d’autres types.
En particulier, il est possible de définir un tableau d’un type défini par l’utilisateur et d’inclure un type défini par l’utilisateur en tant qu’élément d’un type de Tuple.

* Il n’est pas possible de créer des structures de types récursives.
Autrement dit, le type qui définit un type défini par l’utilisateur ne peut pas être un type de tuple qui comprend un élément du type défini par l’utilisateur.
Plus généralement, les types définis par l’utilisateur ne peuvent pas avoir de dépendances cycliques les uns sur les autres. par conséquent, l’ensemble de définitions de type suivant n’est pas valide :

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Types d’opérations et de fonctions

Selon les types `'Tinput` et `'Tresult` :

* `('Tinput => 'Tresult)` est le type de base pour toute *opération* , par exemple `((Qubit, Pauli) => Result)` .
* `('Tinput -> 'Tresult)` est le type de base pour n’importe quelle *fonction* , par exemple `(Int -> Int)` . 

Il s’agit de la *signature* de l’appelable.

* Toutes les Q# callables prennent une valeur unique comme entrée et retournent une valeur unique comme sortie.
* Vous pouvez utiliser des tuples pour les valeurs d’entrée et de sortie.
* Callables qui n’ont pas de résultat, retournent `Unit` .
* Les callables qui n’ont aucune entrée prennent le tuple vide comme entrée.

### <a name="functors"></a>Functors

Les types de *fonction* sont complètement spécifiés par leur signature. Par exemple, une fonction qui calcule le sinus d’un angle aurait le type `(Double -> Double)` . 

Les *opérations* ont certaines caractéristiques supplémentaires qui sont exprimées dans le cadre du type d’opération. Ces caractéristiques incluent des informations sur les *functors* pris en charge par l’opération.
Par exemple, si l’exécution de l’opération dépend de l’état d’autres qubits, elle doit prendre en charge le `Controlled` functor ; si l’opération a un inverse, elle doit prendre en charge `Adjoint` functor.

> [!NOTE]
> Cet article explique en quoi les functors altèrent la signature de l’opération. Pour plus d’informations sur les functors et les opérations, consultez [opérations Q# et fonctions dans ](xref:microsoft.quantum.guide.operationsfunctions). 

Pour exiger la prise en charge de `Controlled` et/ou `Adjoint` de functor dans un type d’opération, vous devez ajouter une annotation indiquant les caractéristiques correspondantes.
L’annotation `is Ctl` (par exemple, `(Qubit => Unit is Ctl)` ) indique que l’opération est contrôlable. Autrement dit, son exécution dépend de l’état d’un autre qubit ou qubits. De même, l’annotation `is Adj` indique que l’opération a un voisint, c’est-à-dire qu’elle peut être « inversée » de sorte que l’application consécutive d’une opération, puis son voisin à un État, laisse l’État inchangé. 

Si vous souhaitez exiger qu’une opération de ce type prenne en charge à la fois le `Adjoint` et le `Controlled` functor, vous pouvez exprimer cela en tant que `(Qubit => Unit is Adj + Ctl)` . Par exemple, l’opération Pauli intégrée <xref:Microsoft.Quantum.Intrinsic.X> a le type `(Qubit => Unit is Adj + Ctl)` . 

Un type d’opération qui ne prend en charge aucun functors est spécifié par son seul type d’entrée et de sortie, sans annotation supplémentaire.

### <a name="type-parameterized-functions-and-operations"></a>Fonctions et opérations de Type-Parameterized

Les types pouvant être appelés peuvent contenir des *paramètres de type* .
Utilisez un symbole préfixé par un guillemet simple pour indiquer un paramètre de type ; par exemple, `'A` est un paramètre de type légal.
Pour plus d’informations et des détails sur la définition de callables paramétrables au type, consultez [opérations et Q# fonctions dans ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).

Un paramètre de type peut apparaître plusieurs fois dans une même signature.
Par exemple, une fonction qui applique une autre fonction à chaque élément d’un tableau et retourne les résultats collectés possède la signature `(('A[], 'A->'A) -> 'A[])` .
De même, une fonction qui retourne la composition de deux opérations possède la signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Quand vous appelez un type paramétrable pouvant être appelé, tous les arguments qui ont le même paramètre de type doivent être du même type.

Q# ne fournit pas de mécanisme permettant de limiter les types possibles qu’un utilisateur peut remplacer par un paramètre de type.

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez vu tous les types qui composent le Q# langage, consultez [expressions de Q# type dans](xref:microsoft.quantum.guide.expressions) pour apprendre à créer et manipuler des expressions de ces différents types.
