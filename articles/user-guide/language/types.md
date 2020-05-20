---
title: Types en Q#
description: 'En savoir plus sur les différents types utilisés dans le langage de programmation Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 4a551ee90a0abb6e42953cf04c7f5a8ca3573f26
ms.sourcegitcommit: 682a4a5f5dd23ca58a4addf62aea4086bb308552
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609139"
---
# <a name="types-in-q"></a><span data-ttu-id="c2f84-103">Types en Q#</span><span class="sxs-lookup"><span data-stu-id="c2f84-103">Types in Q#</span></span>

<span data-ttu-id="c2f84-104">Cette page présente le modèle Q # type et décrit la syntaxe permettant de spécifier et d’utiliser les types.</span><span class="sxs-lookup"><span data-stu-id="c2f84-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="c2f84-105">La page suivante, [expressions de type](xref:microsoft.quantum.guide.expressions), explique comment créer et utiliser des expressions de ces types.</span><span class="sxs-lookup"><span data-stu-id="c2f84-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="c2f84-106">Nous remarquerons que Q # est un langage *fortement typé* , de sorte que l’utilisation prudente de ces types peut aider le compilateur à fournir des garanties fortes sur les programmes Q # au moment de la compilation.</span><span class="sxs-lookup"><span data-stu-id="c2f84-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="c2f84-107">Afin de fournir les garanties les plus fortes possibles, les conversions entre les types dans Q # doivent être explicites à l’aide d’appels à des fonctions qui expriment cette conversion.</span><span class="sxs-lookup"><span data-stu-id="c2f84-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="c2f84-108">Diverses fonctions de ce type sont fournies dans le cadre de l' <xref:microsoft.quantum.convert> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="c2f84-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="c2f84-109">Les casts en types compatibles en revanche se produisent implicitement.</span><span class="sxs-lookup"><span data-stu-id="c2f84-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="c2f84-110">Q # fournit les deux types primitifs, qui peuvent être utilisés directement, ainsi que diverses façons de produire de nouveaux types à partir d’autres types.</span><span class="sxs-lookup"><span data-stu-id="c2f84-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="c2f84-111">Nous décrivons chacun d’entre eux dans le reste de cette section.</span><span class="sxs-lookup"><span data-stu-id="c2f84-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="c2f84-112">Types primitifs</span><span class="sxs-lookup"><span data-stu-id="c2f84-112">Primitive Types</span></span>

<span data-ttu-id="c2f84-113">Le langage Q # fournit plusieurs *types primitifs*, à partir desquels les autres types peuvent être construits :</span><span class="sxs-lookup"><span data-stu-id="c2f84-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="c2f84-114">Le `Int` type représente un entier signé 64 bits, par exemple : `2` , `107` , `-5` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="c2f84-115">Le `BigInt` type représente un entier signé de taille arbitraire, par exemple `2L` , `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="c2f84-116">Ce type est basé sur .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="c2f84-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="c2f84-117">entrer.</span><span class="sxs-lookup"><span data-stu-id="c2f84-117">type.</span></span>
- <span data-ttu-id="c2f84-118">Le `Double` type représente un nombre à virgule flottante double précision, par exemple : `0.0` , `-1.3` , `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="c2f84-119">Le `Bool` type représente une valeur booléenne qui peut être `true` ou `false` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="c2f84-120">Le `Range` type représente une séquence d’entiers, dénotée par `start..step..stop` , où le signalement de l’étape est facultatif.</span><span class="sxs-lookup"><span data-stu-id="c2f84-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="c2f84-121">Cela `start .. stop` correspond à `start..1..stop` , et représente par exemple `1..2..7` la séquence $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="c2f84-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="c2f84-122">Le `String` type est une séquence de caractères Unicode qui est opaque pour l’utilisateur une fois créé.</span><span class="sxs-lookup"><span data-stu-id="c2f84-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="c2f84-123">Ce type est utilisé pour signaler des messages à un hôte classique dans le cas d’une erreur ou d’un événement de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="c2f84-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="c2f84-124">Le type `Unit` est le type qui autorise une seule valeur `()` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="c2f84-125">Ce type est utilisé pour indiquer que la fonction ou l’opération Q # ne retourne aucune information.</span><span class="sxs-lookup"><span data-stu-id="c2f84-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="c2f84-126">Le `Qubit` type représente un bit Quantum ou qubit.</span><span class="sxs-lookup"><span data-stu-id="c2f84-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="c2f84-127">`Qubit`les s sont opaques à l’utilisateur ; la seule opération possible avec eux, à l’exception de leur passage à une autre opération, consiste à tester l’identité (égalité).</span><span class="sxs-lookup"><span data-stu-id="c2f84-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="c2f84-128">Au final, les actions sur `Qubit` s sont implémentées en appelant des instructions intrinsèques sur un processeur Quantum (ou une simulation de celle-ci).</span><span class="sxs-lookup"><span data-stu-id="c2f84-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="c2f84-129">Le `Pauli` type représente l’un des quatre opérateurs Pauli à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="c2f84-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="c2f84-130">Ce type est utilisé pour désigner l’opération de base pour les rotations et pour spécifier l’observable en cours de mesure.</span><span class="sxs-lookup"><span data-stu-id="c2f84-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="c2f84-131">Il s’agit d’un type énuméré qui a quatre valeurs possibles : `PauliI` , `PauliX` , `PauliY` et `PauliZ` , qui sont des constantes de type `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="c2f84-132">Le `Result` type représente le résultat d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="c2f84-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="c2f84-133">Il s’agit d’un type énuméré avec deux valeurs possibles : `One` et `Zero` , qui sont des constantes de type `Result` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="c2f84-134">`Zero`indique que le eigenvalue + 1 a été mesuré ; `One`indique-1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="c2f84-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="c2f84-135">Les constantes,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` et `Zero` sont tous des symboles réservés dans Q #.</span><span class="sxs-lookup"><span data-stu-id="c2f84-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="c2f84-136">Types tableau</span><span class="sxs-lookup"><span data-stu-id="c2f84-136">Array Types</span></span>

<span data-ttu-id="c2f84-137">À partir de n’importe quel type Q # valide `'T` , il existe un type qui représente un tableau de valeurs de type `'T` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="c2f84-138">Ce type de tableau est représenté sous la forme `'T[]` ; par exemple, `Qubit[]` ou `Int[][]` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="c2f84-139">Par exemple, une collection d’entiers est indiquée `Int[]` , tandis qu’un tableau de tableaux de `(Bool, Pauli)` valeurs est indiqué `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="c2f84-140">Dans le deuxième exemple, Notez qu’il s’agit d’un tableau potentiellement en escalier des tableaux, et non d’un tableau rectangulaire à deux dimensions.</span><span class="sxs-lookup"><span data-stu-id="c2f84-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="c2f84-141">Q # ne prend pas en charge les tableaux multidimensionnels rectangulaires.</span><span class="sxs-lookup"><span data-stu-id="c2f84-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="c2f84-142">Une valeur de tableau peut être écrite dans le code source Q # en utilisant des crochets autour des éléments d’un tableau, comme dans `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="c2f84-143">Le type d’un littéral de tableau est déterminé par le type de base commun de tous les éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="c2f84-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="c2f84-144">Les éléments d’un tableau ne peuvent pas être modifiés une fois le tableau créé.</span><span class="sxs-lookup"><span data-stu-id="c2f84-144">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="c2f84-145">Les [instructions Update-and-Assign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) et/ou [copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) peuvent être utilisées pour construire un tableau modifié.</span><span class="sxs-lookup"><span data-stu-id="c2f84-145">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="c2f84-146">Un tableau peut également être créé à partir de sa taille à l’aide du `new` mot clé :</span><span class="sxs-lookup"><span data-stu-id="c2f84-146">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="c2f84-147">Dans les deux cas, une fois qu’un tableau a été construit, la fonction principale `Length` peut être utilisée pour obtenir le nombre d’éléments sous la forme d’un `Int` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-147">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="c2f84-148">Les tableaux peuvent être sous-scriptés à l’aide de crochets, avec des indices `Int` de type ou de type `Range` , pour obtenir des éléments uniques ou de nouveaux tableaux contenant un sous-ensemble des éléments d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="c2f84-148">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="c2f84-149">Les indices de tableaux sont de base zéro :</span><span class="sxs-lookup"><span data-stu-id="c2f84-149">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="c2f84-150">Types de tuples</span><span class="sxs-lookup"><span data-stu-id="c2f84-150">Tuple Types</span></span>

<span data-ttu-id="c2f84-151">À partir de zéro, un ou plusieurs types différents `T0` , `T1` ,..., `Tn` , nous pouvons désigner un nouveau *type de tuple* comme `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-151">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="c2f84-152">Les types utilisés pour construire un nouveau type de tuple peuvent eux-mêmes être des tuples, comme dans `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-152">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="c2f84-153">Toutefois, cette imbrication est toujours finie, car les types de tuple ne peuvent en aucun cas contenir eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="c2f84-153">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="c2f84-154">Les valeurs du nouveau type de tuple sont des tuples formés par des séquences de valeurs de chaque type dans le tuple.</span><span class="sxs-lookup"><span data-stu-id="c2f84-154">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="c2f84-155">Par exemple, `(3, false)` est un tuple dont le type est le type de Tuple `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-155">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="c2f84-156">Il est possible de créer des tableaux de tuples, des tuples de tableaux, des tuples de sous-tuples, etc.</span><span class="sxs-lookup"><span data-stu-id="c2f84-156">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="c2f84-157">À partir de Q # 0,3, `Unit` est le nom du *type* du tuple vide ; `()` est utilisé pour la *valeur*de tuple vide.</span><span class="sxs-lookup"><span data-stu-id="c2f84-157">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="c2f84-158">Les instances de tuple sont immuables.</span><span class="sxs-lookup"><span data-stu-id="c2f84-158">Tuple instances are immutable.</span></span>
<span data-ttu-id="c2f84-159">Q # ne fournit pas de mécanisme permettant de modifier le contenu d’un tuple une fois créé.</span><span class="sxs-lookup"><span data-stu-id="c2f84-159">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="c2f84-160">Les tuples sont un concept puissant utilisé dans Q # pour regrouper des valeurs dans une valeur unique, ce qui facilite leur transmission.</span><span class="sxs-lookup"><span data-stu-id="c2f84-160">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="c2f84-161">En particulier, à l’aide de la notation de tuple, nous pouvons exprimer que chaque opération et Callable prend exactement une entrée et retourne une seule sortie.</span><span class="sxs-lookup"><span data-stu-id="c2f84-161">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="c2f84-162">Équivalence de tuple de Singleton</span><span class="sxs-lookup"><span data-stu-id="c2f84-162">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="c2f84-163">Il est possible de créer un tuple (élément unique) Singleton, `('T1)` , tel que `(5)` ou `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-163">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="c2f84-164">Toutefois, Q # traite un tuple Singleton comme complètement équivalent à une valeur du type délimité.</span><span class="sxs-lookup"><span data-stu-id="c2f84-164">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="c2f84-165">Autrement dit, il n’existe aucune différence entre `5` et `(5)` , ou entre et `5` `(((5)))` , ou entre `(5, (6))` et `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-165">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="c2f84-166">Elle est tout aussi valide pour écrire `(5)+3` en écriture `5+3` , et les deux expressions prennent la valeur `8` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="c2f84-167">Cette équivalence s’applique à tous les usages, y compris les affectations et les expressions.</span><span class="sxs-lookup"><span data-stu-id="c2f84-167">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="c2f84-168">À partir de toute expression, cette même expression entre parenthèses est une expression du même type.</span><span class="sxs-lookup"><span data-stu-id="c2f84-168">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="c2f84-169">Par exemple, `(7)` est une `Int` expression, `([1,2,3])` est une expression de type tableau de `Int` s et `((1,2))` est une expression de type `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-169">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="c2f84-170">En particulier, cela signifie qu’une opération ou une fonction dont le type de tuple d’entrée ou de sortie a un champ peut être considérée comme prendre un seul argument ou retourner une valeur unique.</span><span class="sxs-lookup"><span data-stu-id="c2f84-170">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="c2f84-171">Nous faisons référence à cette propriété en tant qu' _équivalence de tuples Singleton_.</span><span class="sxs-lookup"><span data-stu-id="c2f84-171">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="c2f84-172">Types définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c2f84-172">User-Defined Types</span></span>

<span data-ttu-id="c2f84-173">Une déclaration de type défini par l’utilisateur se compose du mot clé `newtype` , suivi du nom du type défini par l’utilisateur, d’un `=` , d’une spécification de type valide et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="c2f84-173">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="c2f84-174">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c2f84-174">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="c2f84-175">Chaque fichier source Q # peut déclarer un nombre quelconque de types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c2f84-175">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="c2f84-176">Les noms de types doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms d’opération et de fonction.</span><span class="sxs-lookup"><span data-stu-id="c2f84-176">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="c2f84-177">Les types définis par l’utilisateur sont distincts même si les types de base sont identiques.</span><span class="sxs-lookup"><span data-stu-id="c2f84-177">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="c2f84-178">En particulier, il n’existe pas de conversion automatique entre les valeurs de deux types définis par l’utilisateur, même si les types sous-jacents sont identiques.</span><span class="sxs-lookup"><span data-stu-id="c2f84-178">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="c2f84-179">Éléments nommés et anonymes</span><span class="sxs-lookup"><span data-stu-id="c2f84-179">Named vs. anonymous items</span></span>

<span data-ttu-id="c2f84-180">Un fichier Q # peut définir un nouveau type nommé contenant une valeur unique de n’importe quel type légal.</span><span class="sxs-lookup"><span data-stu-id="c2f84-180">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="c2f84-181">Pour tout type de Tuple `T` , nous pouvons déclarer un nouveau type défini par l’utilisateur qui est un sous-type de `T` avec l' `newtype` instruction.</span><span class="sxs-lookup"><span data-stu-id="c2f84-181">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="c2f84-182">Dans l' @"microsoft.quantum.math" espace de noms, par exemple, les nombres complexes sont définis comme un type défini par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="c2f84-182">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="c2f84-183">Cette instruction crée un nouveau type avec deux éléments anonymes de type `Double` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-183">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="c2f84-184">À part les éléments anonymes, les types définis par l’utilisateur prennent également en charge les *éléments nommés* à partir de Q # version 0,7 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c2f84-184">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="c2f84-185">Par exemple, nous aurions pu nommer les éléments to `Re` pour le double représentant la partie réelle d’un nombre complexe et `Im` pour la partie imaginaire :</span><span class="sxs-lookup"><span data-stu-id="c2f84-185">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="c2f84-186">L’attribution d’un nom à un élément dans un type défini par l’utilisateur n’implique pas que tous les éléments doivent être nommés-toute combinaison d’éléments nommés et sans nom est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c2f84-186">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="c2f84-187">En outre, les éléments internes peuvent également être nommés.</span><span class="sxs-lookup"><span data-stu-id="c2f84-187">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="c2f84-188">Le type `Nested` défini ci-dessous par exemple a un type sous-jacent `(Double, (Int, String))` dont seul l’élément de type `Int` est nommé et tous les autres éléments sont anonymes.</span><span class="sxs-lookup"><span data-stu-id="c2f84-188">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="c2f84-189">Les éléments nommés présentent l’avantage de pouvoir accéder directement à l’aide de l' *opérateur d’accès* `::` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-189">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="c2f84-190">En plus de fournir des alias courts pour les types de tuple potentiellement compliqués, l’un des avantages significatifs de la définition de ces types est qu’ils peuvent documenter l’intention d’une valeur particulière.</span><span class="sxs-lookup"><span data-stu-id="c2f84-190">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="c2f84-191">En revenant à l’exemple de `Complex` , vous pouvez également définir des coordonnées polaires 2D comme type défini par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="c2f84-191">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="c2f84-192">Même si `Complex` et `Polar` sont tous deux dotés d’un type sous-jacent `(Double, Double)` , les deux types sont entièrement incompatibles dans Q #, ce qui réduit le risque d’appeler accidentellement une fonction mathématique complexe avec des coordonnées polaires, et vice versa.</span><span class="sxs-lookup"><span data-stu-id="c2f84-192">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="c2f84-193">De cette façon, les types définis par l’utilisateur ont un rôle similaire à celui des enregistrements en F #, par exemple.</span><span class="sxs-lookup"><span data-stu-id="c2f84-193">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="c2f84-194">Accéder aux éléments anonymes avec l’opérateur Unwrap</span><span class="sxs-lookup"><span data-stu-id="c2f84-194">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="c2f84-195">Pour pouvoir accéder à des éléments anonymes en revanche, la valeur encapsulée doit d’abord être extraite à l’aide de l’opérateur postfix `!` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-195">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="c2f84-196">L’opérateur « Unwrap », `!` , permet d’extraire la valeur contenue dans un type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c2f84-196">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="c2f84-197">Le type d’une telle expression « Unwrap » est le type sous-jacent du type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c2f84-197">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="c2f84-198">L’opérateur Unwrap désencapsule une seule couche de renvoi à la ligne.</span><span class="sxs-lookup"><span data-stu-id="c2f84-198">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="c2f84-199">Plusieurs opérateurs Unwrap peuvent être utilisés pour accéder à une valeur encapsuleuse.</span><span class="sxs-lookup"><span data-stu-id="c2f84-199">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="c2f84-200">Exemple :</span><span class="sxs-lookup"><span data-stu-id="c2f84-200">For instance:</span></span>

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

<span data-ttu-id="c2f84-201">Pour plus d’informations sur l’opérateur Unwrap, consultez [expressions de type dans Q #](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="c2f84-201">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="c2f84-202">Création de valeurs de types définis par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="c2f84-202">Creating values of user-defined types</span></span>

<span data-ttu-id="c2f84-203">Les valeurs d’un type défini par l’utilisateur peuvent être créées en appelant le constructeur de type correspondant :</span><span class="sxs-lookup"><span data-stu-id="c2f84-203">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="c2f84-204">Vous pouvez également créer de nouvelles valeurs à partir de valeurs existantes à l’aide d' [expressions de copie et de mise à jour](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="c2f84-204">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="c2f84-205">Comme pour les tableaux, ces expressions copient toutes les valeurs d’élément de l’expression d’origine, à l’exception des éléments nommés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="c2f84-205">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="c2f84-206">Pour ces valeurs, elles sont définies à celles définies sur le côté droit de l’expression.</span><span class="sxs-lookup"><span data-stu-id="c2f84-206">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="c2f84-207">Toutes les autres constructions de langage, comme par exemple les [instructions Update-and-Assign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), qui sont disponibles pour les éléments de tableau existent pour les éléments nommés dans les types définis par l’utilisateur également.</span><span class="sxs-lookup"><span data-stu-id="c2f84-207">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="c2f84-208">Les types définis par l’utilisateur peuvent être utilisés partout où un autre type peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="c2f84-208">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="c2f84-209">En particulier, il est possible de définir un tableau d’un type défini par l’utilisateur et d’inclure un type défini par l’utilisateur en tant qu’élément d’un type de Tuple.</span><span class="sxs-lookup"><span data-stu-id="c2f84-209">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="c2f84-210">Notez qu’il n’est pas possible de créer des structures de types récursives.</span><span class="sxs-lookup"><span data-stu-id="c2f84-210">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="c2f84-211">Autrement dit, le type qui définit un type défini par l’utilisateur ne peut pas être un type de tuple qui comprend un élément du type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c2f84-211">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="c2f84-212">Plus généralement, les types définis par l’utilisateur ne peuvent pas avoir de dépendances cycliques les uns sur les autres. par conséquent, l’ensemble de définitions de type suivant serait illégal :</span><span class="sxs-lookup"><span data-stu-id="c2f84-212">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="c2f84-213">Types d’opérations et de fonctions</span><span class="sxs-lookup"><span data-stu-id="c2f84-213">Operation and Function Types</span></span>

<span data-ttu-id="c2f84-214">Le type de base pour tout appelable est écrit sous la forme `('Tinput => 'Tresult)` ou `('Tinput -> 'Tresult)` , où `'Tinput` et `'Tresult` sont des types.</span><span class="sxs-lookup"><span data-stu-id="c2f84-214">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="c2f84-215">Il s’agit de la *signature* de l’appelable.</span><span class="sxs-lookup"><span data-stu-id="c2f84-215">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="c2f84-216">Tous les Q # callables sont considérés comme une valeur unique comme entrée et retournent une valeur unique comme sortie.</span><span class="sxs-lookup"><span data-stu-id="c2f84-216">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="c2f84-217">Les valeurs d’entrée et de sortie peuvent être des tuples.</span><span class="sxs-lookup"><span data-stu-id="c2f84-217">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="c2f84-218">Callables qui n’ont pas de retour de résultat `Unit` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-218">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="c2f84-219">Les callables qui n’ont aucune entrée prennent le tuple vide comme entrée.</span><span class="sxs-lookup"><span data-stu-id="c2f84-219">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="c2f84-220">La première forme, avec `=>` , est utilisée pour les opérations ; la deuxième forme, avec `->` , pour les fonctions.</span><span class="sxs-lookup"><span data-stu-id="c2f84-220">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="c2f84-221">Par exemple, `((Qubit, Pauli) => Result)` représente la signature d’une opération de mesure qubit unique.</span><span class="sxs-lookup"><span data-stu-id="c2f84-221">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="c2f84-222">Les types de *fonction* sont complètement spécifiés par leur signature.</span><span class="sxs-lookup"><span data-stu-id="c2f84-222">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="c2f84-223">Par exemple, une fonction qui calcule le sinus d’un angle aurait le type `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-223">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="c2f84-224">Les *opérations*---mais pas les fonctions---ont certaines caractéristiques supplémentaires qui sont exprimées dans le cadre du type d’opération.</span><span class="sxs-lookup"><span data-stu-id="c2f84-224">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="c2f84-225">Ces caractéristiques incluent des informations sur les *functors* pris en charge par l’opération.</span><span class="sxs-lookup"><span data-stu-id="c2f84-225">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="c2f84-226">Par exemple, si l’exécution de l’opération peut être conditionnée sur l’état d’autres qubits, elle doit prendre en charge `Controlled` functor ; si l’opération a un inverse, elle doit prendre en charge `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="c2f84-226">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="c2f84-227">Les functors et les opérations sont abordés en détail dans la rubrique [opérations et fonctions de Q #](xref:microsoft.quantum.guide.operationsfunctions), mais ici nous aborderons simplement comment cela modifie la signature d’opération.</span><span class="sxs-lookup"><span data-stu-id="c2f84-227">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="c2f84-228">Pour exiger la prise en charge de `Controlled` et/ou `Adjoint` de functor dans un type d’opération, nous devons ajouter une annotation indiquant les caractéristiques correspondantes.</span><span class="sxs-lookup"><span data-stu-id="c2f84-228">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="c2f84-229">Une annotation `is Ctl` (par exemple, `(Qubit => Unit is Ctl)` ) indique que l’opération est contrôlable---autrement dit, elle est exécutée sur l’état d’un autre qubit ou qubits.</span><span class="sxs-lookup"><span data-stu-id="c2f84-229">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="c2f84-230">De même, `is Adj` indique que l’opération a un voisin ; ou simplement, elle peut être « inversée » de sorte que l’application consécutive d’une opération, puis son voisin à un État, laisse l’État inchangé.</span><span class="sxs-lookup"><span data-stu-id="c2f84-230">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="c2f84-231">Si nous souhaitons exiger qu’une opération de ce type prenne en charge à la fois le `Adjoint` et le `Controlled` functor, nous pouvons exprimer ce qui suit `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-231">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="c2f84-232">Par exemple, l’opération Pauli intégrée <xref:microsoft.quantum.intrinsic.x> a le type `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-232">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="c2f84-233">Un type d’opération qui ne prend en charge aucun functors est spécifié par son seul type d’entrée et de sortie, sans annotation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c2f84-233">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="c2f84-234">Fonctions et opérations paramétrables</span><span class="sxs-lookup"><span data-stu-id="c2f84-234">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="c2f84-235">Les types pouvant être appelés peuvent contenir des paramètres de type.</span><span class="sxs-lookup"><span data-stu-id="c2f84-235">Callable types may contain type parameters.</span></span>
<span data-ttu-id="c2f84-236">Les paramètres de type sont indiqués par un symbole préfixé par un guillemet simple ; par exemple, `'A` est un paramètre de type légal.</span><span class="sxs-lookup"><span data-stu-id="c2f84-236">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="c2f84-237">Pour plus d’informations sur la définition du type-callables paramétrable, reposez-vous sur la page [Operations and Functions in Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) .</span><span class="sxs-lookup"><span data-stu-id="c2f84-237">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="c2f84-238">Un paramètre de type peut apparaître plusieurs fois dans une même signature.</span><span class="sxs-lookup"><span data-stu-id="c2f84-238">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="c2f84-239">Par exemple, une fonction qui applique une autre fonction à chaque élément d’un tableau et retourne les résultats collectés aurait une signature `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-239">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="c2f84-240">De même, une fonction qui retourne la composition de deux opérations peut avoir une signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="c2f84-240">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="c2f84-241">Lors de l’appel d’un pouvant être appelé par un type paramétrable, tous les arguments qui ont le même paramètre de type doivent être du même type.</span><span class="sxs-lookup"><span data-stu-id="c2f84-241">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="c2f84-242">Q # ne fournit pas de mécanisme permettant de limiter les types possibles qui peuvent être remplacés par un paramètre de type.</span><span class="sxs-lookup"><span data-stu-id="c2f84-242">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="whats-next"></a><span data-ttu-id="c2f84-243">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="c2f84-243">What's Next?</span></span>
<span data-ttu-id="c2f84-244">Maintenant que vous avez vu tous les types qui composent le langage Q #, vous pouvez accéder à des [expressions de type dans q #](xref:microsoft.quantum.guide.expressions) pour voir comment créer et manipuler des expressions de ces différents types.</span><span class="sxs-lookup"><span data-stu-id="c2f84-244">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


