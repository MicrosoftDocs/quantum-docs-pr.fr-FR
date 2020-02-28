---
title: 'Types de données Q #'
description: 'Découvrez les différents types utilisés dans le langage de programmation Q #, y compris les types intégrés, les tableaux, les tuples, les opérations, les fonctions et les types définis par l’utilisateur.'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fc4c0b3fed9277c7f9f3ac421330df03c1b30e4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904653"
---
# <a name="the-type-model"></a>Modèle de type

Cette section présente le modèle Q # type et décrit la syntaxe permettant de spécifier et d’utiliser des types.
Nous remarquerons que Q # est un langage *fortement typé* , de sorte que l’utilisation prudente de ces types peut aider le compilateur à fournir des garanties fortes sur les programmes Q # au moment de la compilation.

Afin de fournir les garanties les plus fortes possibles, les conversions entre les types dans Q # doivent être explicites à l’aide d’appels à des fonctions qui expriment cette conversion. Diverses fonctions de ce type sont fournies dans le cadre de l’espace de noms <xref:microsoft.quantum.convert>.
Les casts en types compatibles en revanche se produisent implicitement. 

Q # fournit les deux types primitifs, qui peuvent être utilisés directement, ainsi que diverses façons de produire de nouveaux types à partir d’autres types.
Nous décrivons chacun d’entre eux dans le reste de cette section.

## <a name="primitive-types"></a>Types primitifs

Le langage Q # fournit plusieurs *types primitifs*, à partir desquels les autres types peuvent être construits :

- Le type de `Int` représente un entier signé 64 bits, par exemple : `2`, `107`, `-5`.
- Le type de `BigInt` représente un entier signé de taille arbitraire, par exemple `2L`, `107L``-5L`.
   Ce type est basé sur le .NET <xref:System.Numerics.BigInteger>
   entrer.
- Le type de `Double` représente un nombre à virgule flottante double précision, par exemple : `0.0`, `-1.3`, `4e-7`.
- Le type de `Bool` représente une valeur booléenne qui peut être `true` ou `false`.
- Le type de `Qubit` représente un bit Quantum ou qubit.
   `Qubit`s sont opaques à l’utilisateur ; la seule opération possible avec eux, à l’exception de leur passage à une autre opération, consiste à tester l’identité (égalité).
   Au final, les actions sur `Qubit`s sont implémentées en appelant des instructions intrinsèques sur un processeur Quantum (ou une simulation de celle-ci).
- Le type de `Pauli` représente l’un des quatre opérateurs Pauli à qubit unique.
   Ce type est utilisé pour désigner l’opération de base pour les rotations et pour spécifier l’observable en cours de mesure.
   Il s’agit d’un type énuméré qui a quatre valeurs possibles : `PauliI`, `PauliX`, `PauliY`et `PauliZ`, qui sont des constantes de type `Pauli`.
- Le type de `Result` représente le résultat d’une mesure.
   Il s’agit d’un type énuméré avec deux valeurs possibles : `One` et `Zero`, qui sont des constantes de type `Result`.
   `Zero` indique que le eigenvalue + 1 a été mesuré ; `One` indique-1 eigenvalue.
- Le type de `Range` représente une séquence d’entiers, dénotée par `start..step..stop`, où l’étape est des options. 
   Autrement dit `start .. stop` correspond à `start..1..stop`et, par exemple, `1..2..7` représente la séquence $\{1, 3, 5, 7\}$.
- Le type de `String` est une séquence de caractères Unicode qui est opaque pour l’utilisateur une fois créé.
  Ce type est utilisé pour signaler des messages à un hôte classique dans le cas d’une erreur ou d’un événement de diagnostic.
- Le type de `Unit` est le type qui autorise une seule valeur `()`. 
  Ce type est utilisé pour indiquer que la fonction ou l’opération Q # ne retourne aucune information. 

Les constantes `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`et `Zero` sont tous des symboles réservés dans Q #.

## <a name="array-types"></a>Types tableau

Compte tenu des `'T`de type Q # valides, il existe un type qui représente un tableau de valeurs de type `'T`.
Ce type de tableau est représenté sous la forme `'T[]`; par exemple, `Qubit[]` ou `Int[][]`.
Par exemple, une collection d’entiers est dénotée `Int[]`, alors qu’un tableau de tableaux de valeurs `(Bool, Pauli)` est indiqué `(Bool, Pauli)[][]`.

Dans le deuxième exemple, Notez qu’il s’agit d’un tableau potentiellement en escalier des tableaux, et non d’un tableau rectangulaire à deux dimensions.
Q # ne prend pas en charge les tableaux multidimensionnels rectangulaires.

Une valeur de tableau peut être écrite dans le code source Q # en utilisant des crochets autour des éléments d’un tableau, comme dans `[PauliI, PauliX, PauliY, PauliZ]`.
Le type d’un littéral de tableau est déterminé par le type de base commun de tous les éléments du tableau. 

> [!WARNING]
> Les éléments d’un tableau ne peuvent pas être modifiés une fois le tableau créé.
> Les instructions Update-and-Assign et/ou copy-and-Update peuvent être utilisées pour construire un tableau modifié.

Un tableau peut également être créé à partir de sa taille à l’aide du mot clé `new` :

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Dans les deux cas, une fois qu’un tableau a été construit, la fonction principale `Length` peut être utilisée pour obtenir le nombre d’éléments en tant que `Int`.
Les tableaux peuvent être sous-scriptés à l’aide de crochets, avec des indices de type `Int` ou `Range`pour obtenir des éléments uniques ou de nouveaux tableaux contenant un sous-ensemble des éléments d’un tableau.
Les indices de tableaux sont de base zéro :

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Types de tuples

À partir de zéro, un ou plusieurs types différents `T0`, `T1`,... `Tn`, nous pouvons désigner un nouveau *type de tuple* comme `(T0, T1, ..., Tn)`.
Les types utilisés pour construire un nouveau type de tuple peuvent eux-mêmes être des tuples, comme dans `(Int, (Qubit, Qubit))`.
Toutefois, cette imbrication est toujours finie, car les types de tuple ne peuvent en aucun cas contenir eux-mêmes.

Les valeurs du nouveau type de tuple sont des tuples formés par des séquences de valeurs de chaque type dans le tuple.
Par exemple, `(3, false)` est un tuple dont le type est le type de tuple `(Int, Bool)`.
Il est possible de créer des tableaux de tuples, des tuples de tableaux, des tuples de sous-tuples, etc.

À partir de Q # 0,3, `Unit` est le nom du *type* du tuple vide ; `()` est utilisé pour la *valeur*de tuple vide.

Les instances de tuple sont immuables.
Q # ne fournit pas de mécanisme permettant de modifier le contenu d’un tuple une fois créé.

Les tuples sont un concept puissant utilisé dans Q # pour regrouper des valeurs dans une valeur unique, ce qui facilite leur transmission.
En particulier, à l’aide de la notation de tuple, nous pouvons exprimer que chaque opération et Callable prend exactement une entrée et retourne une seule sortie.

### <a name="singleton-tuple-equivalence"></a>Équivalence de tuple de Singleton

Il est possible de créer un tuple (élément unique) Singleton, `('T1)`, tel que `(5)` ou `([1,2,3])`.
Toutefois, Q # traite un tuple Singleton comme complètement équivalent à une valeur du type délimité.
Autrement dit, il n’y a aucune différence entre `5` et `(5)`, ou entre `5` et `(((5)))`, ou entre `(5, (6))` et `(5, 6)`.

Cette équivalence s’applique à tous les usages, y compris les affectations et les expressions.
Elle est tout aussi valide pour écrire des `(5)+3` en tant que pour écrire des `5+3`, et les deux expressions prennent la valeur `8`.
En particulier, cela signifie qu’une opération ou une fonction dont le type de tuple d’entrée ou de sortie a un champ peut être considérée comme prendre un seul argument ou retourner une valeur unique.

Nous faisons référence à cette propriété en tant qu' _équivalence de tuples Singleton_.

## <a name="user-defined-types"></a>Types définis par l'utilisateur

Un fichier Q # peut définir un nouveau type nommé contenant une valeur unique de n’importe quel type légal.
Pour tout type de tuple `T`, nous pouvons déclarer un nouveau type défini par l’utilisateur qui est un sous-type de `T` avec l’instruction `newtype`.
Dans l’espace de noms @"microsoft.quantum.math", par exemple, les nombres complexes sont définis comme un type défini par l’utilisateur :

```qsharp
newtype Complex = (Double, Double);
```

Cette instruction crée un nouveau type avec deux éléments anonymes de type `Double`.   
Outre les éléments anonymes, les types définis par l’utilisateur prennent également en charge les éléments nommés comme Q # version 0,7 ou ultérieure. Par exemple, nous aurions pu nommer le `Re` to items pour le double représentant la partie réelle d’un nombre complexe et `Im` pour la partie imaginaire : 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
L’attribution d’un nom à un élément dans un type défini par l’utilisateur n’implique pas que tous les éléments doivent être nommés-toute combinaison d’éléments nommés et sans nom est prise en charge. En outre, les éléments internes peuvent également être nommés.
Le type `Nested` comme indiqué ci-dessous, par exemple, a un type sous-jacent `(Double, (Int, String))`dont seul l’élément de type `Int` est nommé et tous les autres éléments sont anonymes. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Les éléments nommés présentent l’avantage de pouvoir être accessibles directement par le biais de l’opérateur d’accès `::`. 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Pour pouvoir accéder à des éléments anonymes en revanche, la valeur encapsulée doit d’abord être extraite à l’aide de l’opérateur postfix `!`.
L’opérateur « Unwrap », `!`, permet d’extraire la valeur contenue dans un type défini par l’utilisateur.
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

Pour plus d’informations, consultez la section sur les [expressions de désencapsulation](xref:microsoft.quantum.language.expressions#unwrap-expressions) et la [priorité des opérateurs](xref:microsoft.quantum.language.expressions#operator-precedence) .

Les valeurs d’un type défini par l’utilisateur peuvent être créées en appelant le constructeur de type correspondant :

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Vous pouvez également créer de nouvelles valeurs à partir de valeurs existantes à l’aide d' [expressions de copie et de mise à jour](xref:microsoft.quantum.language.expressions#copy-and-update-expressions). Comme pour les tableaux, ces expressions copient toutes les valeurs d’élément de l’expression d’origine, à l’exception des éléments nommés spécifiés. Pour ces valeurs, elles sont définies à celles définies sur le côté droit de l’expression. Toutes les autres constructions de langage, comme par exemple les [instructions Update-and-Assign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), qui sont disponibles pour les éléments de tableau existent pour les éléments nommés dans les types définis par l’utilisateur.

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

Il n’est pas possible de créer des structures de types récursives.
Autrement dit, le type qui définit un type défini par l’utilisateur ne peut pas être un type de tuple qui comprend un élément du type défini par l’utilisateur.
Plus généralement, les types définis par l’utilisateur ne peuvent pas avoir de dépendances cycliques les uns sur les autres. par conséquent, l’ensemble de définitions de type suivant serait illégal :

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

En plus de fournir des alias courts pour les types de tuple potentiellement compliqués, l’un des avantages significatifs de la définition de ces types est qu’ils peuvent documenter l’intention d’une valeur particulière.
En revenant à l’exemple de `Complex`, il est possible d’avoir également défini des coordonnées polaires 2D comme type défini par l’utilisateur :

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Même si les deux `Complex` et `Polar` ont tous deux un type sous-jacent `(Double, Double)`, les deux types sont entièrement incompatibles dans Q #, ce qui réduit le risque d’appeler accidentellement une fonction mathématique complexe avec des coordonnées polaires, et vice versa.
De cette façon, les types définis par l’utilisateur ont un rôle similaire à F# celui des enregistrements dans, par exemple. 


## <a name="operation-and-function-types"></a>Types d’opérations et de fonctions

Une _opération_ Q # est une sous-routine Quantum.
Autrement dit, il s’agit d’une routine appelable qui contient des opérations quantiques.

Une _fonction_ Q # est une sous-routine classique utilisée dans un algorithme Quantum.
Elle peut contenir du code classique, mais aucune opération Quantum.
Plus précisément, les fonctions ne peuvent pas allouer ou emprunter des qubits, ni appeler des opérations.
Toutefois, il est possible de leur transmettre des opérations ou des qubits de traitement.
Les fonctions sont donc entièrement déterministes dans le sens où l’appel de ces mêmes arguments produira toujours le même résultat. 

Ensemble, les opérations et les fonctions sont appelées _callables_.  Vous pouvez voir quelques [exemples](#examples) ci-dessous.

Tous les Q # callables sont considérés comme une valeur unique comme entrée et retournent une valeur unique comme sortie.
Les valeurs d’entrée et de sortie peuvent être des tuples.
Callables qui n’ont pas de résultat de retour `Unit`.
Les callables qui n’ont aucune entrée prennent le tuple vide comme entrée.

Le type de base pour tout appelable est écrit sous la forme `('Tinput => 'Tresult)` ou `('Tinput -> 'Tresult)`, où `'Tinput` et `'Tresult` sont des types.
La première forme, avec `=>`, est utilisée pour les opérations ; deuxième forme, avec `->`, pour les fonctions.
Par exemple, `((Qubit, Pauli) => Result)` représente la signature d’une opération de mesure qubit unique.

Les types de fonction sont complètement spécifiés par leur signature.
Par exemple, une fonction qui calcule le sinus d’un angle aurait un type `(Double -> Double)`.

Les opérations, mais pas les fonctions, ont certaines _caractéristiques_ supplémentaires qui sont exprimées dans le cadre du type d’opération. Ces caractéristiques incluent des informations sur les functors pris en charge par l’opération.
Les functors sont des méta-opérations qui génèrent une spécialisation d’une opération de base. consultez les [functors](#functors), ci-dessous.

Les types d’opérations sont spécifiés par leur type d’entrée, leur type de sortie et leurs caractéristiques.    
Pour exiger la prise en charge des `Controlled` et/ou `Adjoint` functor dans un type d’opération, nous devons ajouter une annotation indiquant les caractéristiques correspondantes.
Une `is Ctl` d’annotation, par exemple, indique que l’opération est contrôlable. Si nous souhaitons exiger qu’une opération de ce type prenne en charge les `Adjoint` et `Controlled` functor, nous pouvons exprimer cela comme `(Qubit => Unit is Adj + Ctl)`. Les caractéristiques d’opération utilisées `Adj` et `Ctl` strictement parlant sont deux ensembles prédéfinis d’étiquettes, où chaque étiquette indique une caractéristique d’opération particulière comme par exemple, la prise en charge d’un functor particulier.
Par conséquent, `+` est utilisé pour indiquer l’Union de ces deux jeux, et `*` est utilisé pour indiquer l’intersection, c’est-à-dire les étiquettes qui sont communes aux deux ensembles.  

Par exemple, l’opération de `X` Pauli a le type `(Qubit => Unit is Adj + Ctl)`.
Un type d’opération qui ne prend en charge aucun functors est spécifié par son seul type d’entrée et de sortie, sans annotation supplémentaire.


### <a name="type-parameterized-functions-and-operations"></a>Fonctions et opérations paramétrables

Les types pouvant être appelés peuvent contenir des paramètres de type.
Les paramètres de type sont indiqués par un symbole préfixé par un guillemet simple ; par exemple, `'A` est un paramètre de type légal.

Un paramètre de type peut apparaître plusieurs fois dans une même signature.
Par exemple, une fonction qui applique une autre fonction à chaque élément d’un tableau et retourne les résultats collectés aurait une signature `(('A[], 'A->'A) -> 'A[])`.
De même, une fonction qui retourne la composition de deux opérations peut avoir une signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.

Lors de l’appel d’un pouvant être appelé par un type paramétrable, tous les arguments qui ont le même paramètre de type doivent être du même type.

Q # ne fournit pas de mécanisme permettant de limiter les types possibles qui peuvent être remplacés par un paramètre de type.

### <a name="type-compatibility"></a>Compatibilité de type

Une opération avec des functors supplémentaires pris en charge peut être utilisée partout où une opération avec moins d’functors, mais la même signature est attendue.
Par exemple, une opération de type `(Qubit => Unit is Adj)` peut être utilisée partout où une opération de type `(Qubit => Unit)` est attendue.

Q # est covariant en ce qui concerne les types de retour pouvant être appelés : un pouvant être appelé qui retourne un type `'A` est compatible avec un pouvant être appelé avec le même type d’entrée et un type de résultat qui `'A` est compatible avec.

Q # est contravariant en ce qui concerne les types d’entrée : un pouvant être appelé qui accepte un type `'A` comme entrée est compatible avec un pouvant être appelé avec le même type de résultat et un type d’entrée compatible avec `'A`.

Autrement dit, étant donné les définitions suivantes :

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

les conditions suivantes sont vraies :

- La fonction `ConjugateInvertWith` peut être appelée avec un argument `inner` de `Invert` ou `ApplyUnitary`.
- La fonction `ConjugateUnitaryWith` peut être appelée avec un argument `inner` de `ApplyUnitary`, mais pas `Invert`.
- Une valeur de type `(Qubit[] => Unit is Adj + Ctl)` peut être retournée à partir de `ConjugateInvertWith`.

> [!IMPORTANT]
> Q # 0,3 introduit une différence significative dans le comportement des types définis par l’utilisateur.

Les types définis par l’utilisateur sont traités comme une version encapsulée du type sous-jacent, plutôt qu’en tant que sous-type.
Cela signifie qu’une valeur d’un type défini par l’utilisateur n’est pas utilisable quand une valeur du type sous-jacent est attendue.

### <a name="functors"></a>Functors

Un functor dans Q # est une fabrique qui définit une nouvelle opération à partir d’une autre opération.
Les functors ont accès à l’implémentation de l’opération de base lors de la définition de l’implémentation de la nouvelle opération.
Ainsi, les functors peuvent exécuter des fonctions plus complexes que les fonctions de niveau supérieur traditionnelles.

Les functors n’ont pas de représentation dans le système Q # type. Il n’est donc actuellement pas possible de les lier à une variable ou de les passer comme arguments. 

Un functor est utilisé en l’appliquant à une opération, en retournant une nouvelle opération.
Par exemple, l’opération qui résulte de l’application de l' `Adjoint` functor à l’opération `Y` est écrite en tant que `Adjoint Y`.
La nouvelle opération peut ensuite être appelée comme toute autre opération.
Ainsi, `Adjoint Y(q1)` applique le functor joint à l’opération `Y` pour générer une nouvelle opération et applique cette nouvelle opération à `q1`.

De même, `Controlled X(controls, target)` applique la functor contrôlée à l’opération `X` pour générer une nouvelle opération et applique cette nouvelle opération à `controls` et `target`.

Les deux functors standard de Q # sont `Adjoint` et `Controlled`.

#### <a name="adjoint"></a>Voisin

Dans Quantum Computing, le voisin d’une opération est la complexe conjugué de l’opération.
Pour les opérations qui implémentent un opérateur unitaire, le voisin est l’inverse de l’opération.
Pour une opération simple qui appelle simplement une séquence d’autres opérations unitaires sur un ensemble de qubits, le voisint peut être calculé en appliquant les adjoints des sous-opérations sur le même qubits, dans l’ordre inverse.

En fonction d’une expression d’opération, une nouvelle expression d’opération peut être formée à l’aide de l' `Adjoint` functor.
Par exemple, `Adjoint QFT` désigne le voisin du `QFT` opération.
La nouvelle opération a la même signature et le même type que l’opération de base.
En particulier, la nouvelle opération autorise également `Adjoint`et autorise `Controlled` si et uniquement si l’opération de base a été effectuée.

Le functor de l’Contigut est son propre inverse ; autrement dit, `Adjoint Adjoint Op` est toujours identique à `Op`.

#### <a name="controlled"></a>Contrôl

La version contrôlée d’une opération est une nouvelle opération qui applique efficacement l’opération de base uniquement si tous les qubits de contrôle sont dans un état spécifié.
Si le contrôle qubits est en superposition, l’opération de base est appliquée de manière cohérente à la partie appropriée de la superposition.
Ainsi, les opérations contrôlées sont souvent utilisées pour générer l’enchevêtrement.

Dans Q #, les versions contrôlées prennent toujours un tableau de qubits de contrôle, et l’état spécifié est toujours pour tous les qubits de contrôle dans l’état de `One` de calcul (`PauliZ`), $ \ket{1}$.
Le contrôle basé sur d’autres États peut être obtenu en appliquant l’opération unitaire appropriée à l’qubits de contrôle avant l’opération contrôlée, puis en appliquant les inversions de l’opération unitaire après l’opération contrôlée.
Par exemple, l’application d’une opération de `X` à un contrôle qubit avant et après une opération contrôlée entraînera le contrôle de l’opération sur l’État `Zero` ($ \ket{0}$) pour ce qubit ; l’application d’une `H` opération avant et après contrôle l’état de la `One` `PauliX`, c’est-à-dire-1 eigenvalue de Pauli X, $ \ket{-} \mathrel{ : =} (\ket{0}-\ket{1})/\sqrt{2}$ au lieu de l’État `PauliZ` `One`.

En fonction d’une expression d’opération, une nouvelle expression d’opération peut être formée à l’aide de l' `Controlled` functor.
La signature de la nouvelle opération est basée sur la signature de l’opération d’origine.
Le type de résultat est le même, mais le type d’entrée est un double Tuple avec un tableau qubit qui contient les qubit de contrôle comme premier élément et les arguments de l’opération d’origine comme second élément.
La nouvelle opération prend en charge `Controlled`et prendra en charge `Adjoint` si et uniquement si l’opération d’origine a été effectuée.

Si l’opération d’origine n’a pris qu’un seul argument, l’équivalence du tuple de Singleton sera alors lue ici.
Par exemple, `Controlled X` est la version contrôlée de l’opération `X`.
`X` a le type `(Qubit => Unit is Adj + Ctl)`, donc `Controlled X` a le type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; en raison de l’équivalence des tuples Singleton, il est identique à `((Qubit[], Qubit) => Unit is Adj + Ctl)`.

Si l’opération de base a pris plusieurs arguments, n’oubliez pas de placer les arguments correspondants de la version contrôlée de l’opération entre parenthèses pour les convertir en Tuple.
Par exemple, `Controlled Rz` est la version contrôlée de l’opération `Rz`.
`Rz` est de type `((Double, Qubit) => Unit is Adj + Ctl)`, `Controlled Rz` est donc de type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.
Par conséquent, `Controlled Rz(controls, (0.1, target))` serait un appel valide de `Controlled Rz` (Notez les parenthèses autour de `0.1, target`).

En guise d’autre exemple, `CNOT(control, target)` peut être implémentée en tant que `Controlled X([control], target)`. Si une cible doit être contrôlée par deux qubits de contrôle (CCNOT), nous pouvons utiliser `Controlled X([control1, control2], target)` instruction.

### <a name="examples"></a>Exemples

Cet exemple d’opération Q # provient de l’exemple [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) . Dans les opérations, nous pouvons allouer qubits et utiliser des opérations de Quantum sur ces qubits, telles que `H` et `X`:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

Cet exemple de fonction provient de l’exemple [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) . Il contient du code purement classique. Vous pouvez voir que, contrairement à l’exemple ci-dessus, aucun qubits n’est alloué et aucune opération de Quantum n’est utilisée.

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

Il est également possible qu’une fonction soit passée qubits pour traitement, comme dans cet exemple à partir de l’exemple [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) . Les qubits sont passés à la fonction et utilisés pour le traitement, mais à aucun moment les États qubit eux-mêmes ne sont pas modifiés.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
