---
title: 'Types dans Q #'
description: 'En savoir plus sur les différents types utilisés dans le langage de programmation Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 58370193bd62e306197a9e07c28f8611f043e55c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431136"
---
# <a name="types-in-q"></a>Types dans Q #

Cette page présente le modèle Q # type et décrit la syntaxe permettant de spécifier et d’utiliser les types.
La page suivante, [expressions de type](xref:microsoft.quantum.guide.expressions), explique comment créer et utiliser des expressions de ces types.

Nous remarquerons que Q # est un langage *fortement typé* , de sorte que l’utilisation prudente de ces types peut aider le compilateur à fournir des garanties fortes sur les programmes Q # au moment de la compilation.
Afin de fournir les garanties les plus fortes possibles, les conversions entre les types dans Q # doivent être explicites à l’aide d’appels à des fonctions qui expriment cette conversion. Diverses fonctions de ce type sont fournies dans le cadre de l' <xref:microsoft.quantum.convert> espace de noms.
Les casts en types compatibles en revanche se produisent implicitement. 

Q # fournit les deux types primitifs, qui peuvent être utilisés directement, ainsi que diverses façons de produire de nouveaux types à partir d’autres types.
Nous décrivons chacun d’entre eux dans le reste de cette section.

## <a name="primitive-types"></a>Types primitifs

Le langage Q # fournit plusieurs *types primitifs*, à partir desquels les autres types peuvent être construits :

- Le `Int` type représente un entier signé 64 bits, par exemple : `2` , `107` , `-5` .
- Le `BigInt` type représente un entier signé de taille arbitraire, par exemple `2L` , `107L` `-5L` .
   Ce type est basé sur .NET<xref:System.Numerics.BigInteger>
   entrer.
- Le `Double` type représente un nombre à virgule flottante double précision, par exemple : `0.0` , `-1.3` , `4e-7` .
- Le `Bool` type représente une valeur booléenne qui peut être `true` ou `false` .
- Le `Range` type représente une séquence d’entiers, dénotée par `start..step..stop` , où l’étape est des options. 
   Cela `start .. stop` correspond à `start..1..stop` , et représente par exemple `1..2..7` la séquence $ \{ 1, 3, 5, 7 \} $.
- Le `String` type est une séquence de caractères Unicode qui est opaque pour l’utilisateur une fois créé.
  Ce type est utilisé pour signaler des messages à un hôte classique dans le cas d’une erreur ou d’un événement de diagnostic.
- Le type `Unit` est le type qui autorise une seule valeur `()` . 
  Ce type est utilisé pour indiquer que la fonction ou l’opération Q # ne retourne aucune information. 
- Le `Qubit` type représente un bit Quantum ou qubit.
   `Qubit`les s sont opaques à l’utilisateur ; la seule opération possible avec eux, à l’exception de leur passage à une autre opération, consiste à tester l’identité (égalité).
   Au final, les actions sur `Qubit` s sont implémentées en appelant des instructions intrinsèques sur un processeur Quantum (ou une simulation de celle-ci).
- Le `Pauli` type représente l’un des quatre opérateurs Pauli à qubit unique.
   Ce type est utilisé pour désigner l’opération de base pour les rotations et pour spécifier l’observable en cours de mesure.
   Il s’agit d’un type énuméré qui a quatre valeurs possibles : `PauliI` , `PauliX` , `PauliY` et `PauliZ` , qui sont des constantes de type `Pauli` .
- Le `Result` type représente le résultat d’une mesure.
   Il s’agit d’un type énuméré avec deux valeurs possibles : `One` et `Zero` , qui sont des constantes de type `Result` .
   `Zero`indique que le eigenvalue + 1 a été mesuré ; `One`indique-1 eigenvalue.

Les constantes,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` et `Zero` sont tous des symboles réservés dans Q #.

## <a name="array-types"></a>Types tableau

À partir de n’importe quel type Q # valide `'T` , il existe un type qui représente un tableau de valeurs de type `'T` .
Ce type de tableau est représenté sous la forme `'T[]` ; par exemple, `Qubit[]` ou `Int[][]` .
Par exemple, une collection d’entiers est indiquée `Int[]` , tandis qu’un tableau de tableaux de `(Bool, Pauli)` valeurs est indiqué `(Bool, Pauli)[][]` .

Dans le deuxième exemple, Notez qu’il s’agit d’un tableau potentiellement en escalier des tableaux, et non d’un tableau rectangulaire à deux dimensions.
Q # ne prend pas en charge les tableaux multidimensionnels rectangulaires.

Une valeur de tableau peut être écrite dans le code source Q # en utilisant des crochets autour des éléments d’un tableau, comme dans `[PauliI, PauliX, PauliY, PauliZ]` .
Le type d’un littéral de tableau est déterminé par le type de base commun de tous les éléments du tableau. 

> [!WARNING]
> Les éléments d’un tableau ne peuvent pas être modifiés une fois le tableau créé.
> Les [instructions Update-and-Assign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) et/ou [copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) peuvent être utilisées pour construire un tableau modifié.

Un tableau peut également être créé à partir de sa taille à l’aide du `new` mot clé :

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Dans les deux cas, une fois qu’un tableau a été construit, la fonction principale `Length` peut être utilisée pour obtenir le nombre d’éléments sous la forme d’un `Int` .
Les tableaux peuvent être sous-scriptés à l’aide de crochets, avec des indices `Int` de type ou de type `Range` , pour obtenir des éléments uniques ou de nouveaux tableaux contenant un sous-ensemble des éléments d’un tableau.
Les indices de tableaux sont de base zéro :

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Types de tuples

À partir de zéro, un ou plusieurs types différents `T0` , `T1` ,..., `Tn` , nous pouvons désigner un nouveau *type de tuple* comme `(T0, T1, ..., Tn)` .
Les types utilisés pour construire un nouveau type de tuple peuvent eux-mêmes être des tuples, comme dans `(Int, (Qubit, Qubit))` .
Toutefois, cette imbrication est toujours finie, car les types de tuple ne peuvent en aucun cas contenir eux-mêmes.

Les valeurs du nouveau type de tuple sont des tuples formés par des séquences de valeurs de chaque type dans le tuple.
Par exemple, `(3, false)` est un tuple dont le type est le type de Tuple `(Int, Bool)` .
Il est possible de créer des tableaux de tuples, des tuples de tableaux, des tuples de sous-tuples, etc.

À partir de Q # 0,3, `Unit` est le nom du *type* du tuple vide ; `()` est utilisé pour la *valeur*de tuple vide.

Les instances de tuple sont immuables.
Q # ne fournit pas de mécanisme permettant de modifier le contenu d’un tuple une fois créé.

Les tuples sont un concept puissant utilisé dans Q # pour regrouper des valeurs dans une valeur unique, ce qui facilite leur transmission.
En particulier, à l’aide de la notation de tuple, nous pouvons exprimer que chaque opération et Callable prend exactement une entrée et retourne une seule sortie.

### <a name="singleton-tuple-equivalence"></a>Équivalence de tuple de Singleton

Il est possible de créer un tuple (élément unique) Singleton, `('T1)` , tel que `(5)` ou `([1,2,3])` .
Toutefois, Q # traite un tuple Singleton comme complètement équivalent à une valeur du type délimité.
Autrement dit, il n’existe aucune différence entre `5` et `(5)` , ou entre et `5` `(((5)))` , ou entre `(5, (6))` et `(5, 6)` .
Elle est tout aussi valide pour écrire `(5)+3` en écriture `5+3` , et les deux expressions prennent la valeur `8` .

Cette équivalence s’applique à tous les usages, y compris les affectations et les expressions.
À partir de toute expression, cette même expression entre parenthèses est une expression du même type.
Par exemple, `(7)` est une `Int` expression, `([1,2,3])` est une expression de type tableau de `Int` s et `((1,2))` est une expression de type `(Int, Int)` .

En particulier, cela signifie qu’une opération ou une fonction dont le type de tuple d’entrée ou de sortie a un champ peut être considérée comme prendre un seul argument ou retourner une valeur unique.

Nous faisons référence à cette propriété en tant qu' _équivalence de tuples Singleton_.


## <a name="user-defined-types"></a>Types définis par l'utilisateur

Une déclaration de type défini par l’utilisateur se compose du mot clé `newtype` , suivi du nom du type défini par l’utilisateur, d’un `=` , d’une spécification de type valide et d’un point-virgule de fin.

Par exemple :

```qsharp
newtype PairOfInts = (Int, Int);
```

Chaque fichier source Q # peut déclarer un nombre quelconque de types définis par l’utilisateur.
Les noms de types doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms d’opération et de fonction.

Les types définis par l’utilisateur sont distincts même si les types de base sont identiques.
En particulier, il n’existe pas de conversion automatique entre les valeurs de deux types définis par l’utilisateur, même si les types sous-jacents sont identiques.

### <a name="named-vs-anonymous-items"></a>Éléments nommés et anonymes

Un fichier Q # peut définir un nouveau type nommé contenant une valeur unique de n’importe quel type légal.
Pour tout type de Tuple `T` , nous pouvons déclarer un nouveau type défini par l’utilisateur qui est un sous-type de `T` avec l' `newtype` instruction.
Dans l' @"microsoft.quantum.math" espace de noms, par exemple, les nombres complexes sont définis comme un type défini par l’utilisateur :

```qsharp
newtype Complex = (Double, Double);
```
Cette instruction crée un nouveau type avec deux éléments anonymes de type `Double` .   

À part les éléments anonymes, les types définis par l’utilisateur prennent également en charge les *éléments nommés* à partir de Q # version 0,7 ou ultérieure. Par exemple, nous aurions pu nommer les éléments to `Re` pour le double représentant la partie réelle d’un nombre complexe et `Im` pour la partie imaginaire : 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
L’attribution d’un nom à un élément dans un type défini par l’utilisateur n’implique pas que tous les éléments doivent être nommés-toute combinaison d’éléments nommés et sans nom est prise en charge. En outre, les éléments internes peuvent également être nommés.
Le type `Nested` défini ci-dessous par exemple a un type sous-jacent `(Double, (Int, String))` dont seul l’élément de type `Int` est nommé et tous les autres éléments sont anonymes. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Les éléments nommés présentent l’avantage de pouvoir accéder directement à l’aide de l' *opérateur d’accès* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

En plus de fournir des alias courts pour les types de tuple potentiellement compliqués, l’un des avantages significatifs de la définition de ces types est qu’ils peuvent documenter l’intention d’une valeur particulière.
En revenant à l’exemple de `Complex` , vous pouvez également définir des coordonnées polaires 2D comme type défini par l’utilisateur :

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Même si `Complex` et `Polar` sont tous deux dotés d’un type sous-jacent `(Double, Double)` , les deux types sont entièrement incompatibles dans Q #, ce qui réduit le risque d’appeler accidentellement une fonction mathématique complexe avec des coordonnées polaires, et vice versa.
De cette façon, les types définis par l’utilisateur ont un rôle similaire à celui des enregistrements en F #, par exemple. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Accéder aux éléments anonymes avec l’opérateur Unwrap

Pour pouvoir accéder à des éléments anonymes en revanche, la valeur encapsulée doit d’abord être extraite à l’aide de l’opérateur postfix `!` .
L’opérateur « Unwrap », `!` , permet d’extraire la valeur contenue dans un type défini par l’utilisateur.
Le type d’une telle expression « Unwrap » est le type sous-jacent du type défini par l’utilisateur. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

L’opérateur Unwrap désencapsule une seule couche de renvoi à la ligne.
Plusieurs opérateurs Unwrap peuvent être utilisés pour accéder à une valeur encapsuleuse.

Exemple :

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

Pour plus d’informations sur l’opérateur Unwrap, consultez [expressions de type dans Q #](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Création de valeurs de types définis par l’utilisateur

Les valeurs d’un type défini par l’utilisateur peuvent être créées en appelant le constructeur de type correspondant :

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Vous pouvez également créer de nouvelles valeurs à partir de valeurs existantes à l’aide d' [expressions de copie et de mise à jour](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Comme pour les tableaux, ces expressions copient toutes les valeurs d’élément de l’expression d’origine, à l’exception des éléments nommés spécifiés. Pour ces valeurs, elles sont définies à celles définies sur le côté droit de l’expression. Toutes les autres constructions de langage, comme par exemple les [instructions Update-and-Assign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), qui sont disponibles pour les éléments de tableau existent pour les éléments nommés dans les types définis par l’utilisateur également.

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

Les types définis par l’utilisateur peuvent être utilisés partout où un autre type peut être utilisé.
En particulier, il est possible de définir un tableau d’un type défini par l’utilisateur et d’inclure un type défini par l’utilisateur en tant qu’élément d’un type de Tuple.

Notez qu’il n’est pas possible de créer des structures de types récursives.
Autrement dit, le type qui définit un type défini par l’utilisateur ne peut pas être un type de tuple qui comprend un élément du type défini par l’utilisateur.
Plus généralement, les types définis par l’utilisateur ne peuvent pas avoir de dépendances cycliques les uns sur les autres. par conséquent, l’ensemble de définitions de type suivant serait illégal :

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Types d’opérations et de fonctions

Le type de base pour tout appelable est écrit sous la forme `('Tinput => 'Tresult)` ou `('Tinput -> 'Tresult)` , où `'Tinput` et `'Tresult` sont des types.
Il s’agit de la *signature* de l’appelable.

Tous les Q # callables sont considérés comme une valeur unique comme entrée et retournent une valeur unique comme sortie.
Les valeurs d’entrée et de sortie peuvent être des tuples.
Callables qui n’ont pas de retour de résultat `Unit` .
Les callables qui n’ont aucune entrée prennent le tuple vide comme entrée.

> [!NOTE]
> La première forme, avec `=>` , est utilisée pour les opérations ; la deuxième forme, avec `->` , pour les fonctions.
> Par exemple, `((Qubit, Pauli) => Result)` représente la signature d’une opération de mesure qubit unique.
Les types de *fonction* sont complètement spécifiés par leur signature.
Par exemple, une fonction qui calcule le sinus d’un angle aurait le type `(Double -> Double)` .

Les *opérations*---mais pas les fonctions---ont certaines caractéristiques supplémentaires qui sont exprimées dans le cadre du type d’opération. Ces caractéristiques incluent des informations sur les *functors* pris en charge par l’opération.
Par exemple, si l’exécution de l’opération peut être conditionnée sur l’état d’autres qubits, elle doit prendre en charge `Controlled` functor ; si l’opération a un inverse, elle doit prendre en charge `Adjoint` functor. Les functors et les opérations sont abordés en détail dans la rubrique [opérations et fonctions de Q #](xref:microsoft.quantum.guide.operationsfunctions), mais ici nous aborderons simplement comment cela modifie la signature d’opération.

Pour exiger la prise en charge de `Controlled` et/ou `Adjoint` de functor dans un type d’opération, nous devons ajouter une annotation indiquant les caractéristiques correspondantes.
Une annotation `is Ctl` (par exemple, `(Qubit => Unit is Ctl)` ) indique que l’opération est contrôlable---autrement dit, elle est exécutée sur l’état d’un autre qubit ou qubits. De même, `is Adj` indique que l’opération a un voisin ; ou simplement, elle peut être « inversée » de sorte que l’application consécutive d’une opération, puis son voisin à un État, laisse l’État inchangé. 

Si nous souhaitons exiger qu’une opération de ce type prenne en charge à la fois le `Adjoint` et le `Controlled` functor, nous pouvons exprimer ce qui suit `(Qubit => Unit is Adj + Ctl)` . Par exemple, l’opération Pauli intégrée <xref:microsoft.quantum.intrinsic.x> a le type `(Qubit => Unit is Adj + Ctl)` . 

Un type d’opération qui ne prend en charge aucun functors est spécifié par son seul type d’entrée et de sortie, sans annotation supplémentaire.

### <a name="type-parameterized-functions-and-operations"></a>Fonctions et opérations paramétrables

Les types pouvant être appelés peuvent contenir des paramètres de type.
Les paramètres de type sont indiqués par un symbole préfixé par un guillemet simple ; par exemple, `'A` est un paramètre de type légal.
Pour plus d’informations sur la définition du type-callables paramétrable, reposez-vous sur la page [Operations and Functions in Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) .

Un paramètre de type peut apparaître plusieurs fois dans une même signature.
Par exemple, une fonction qui applique une autre fonction à chaque élément d’un tableau et retourne les résultats collectés aurait une signature `(('A[], 'A->'A) -> 'A[])` .
De même, une fonction qui retourne la composition de deux opérations peut avoir une signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Lors de l’appel d’un pouvant être appelé par un type paramétrable, tous les arguments qui ont le même paramètre de type doivent être du même type.

Q # ne fournit pas de mécanisme permettant de limiter les types possibles qui peuvent être remplacés par un paramètre de type.

## <a name="whats-next"></a>Étape suivante
Maintenant que vous avez vu tous les types qui composent le langage Q #, vous pouvez accéder à des [expressions de type dans q #](xref:microsoft.quantum.guide.expressions) pour voir comment créer et manipuler des expressions de ces différents types.


