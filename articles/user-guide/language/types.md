---
title: Types en Q#
description: 'En savoir plus sur les différents types utilisés dans le langage de programmation Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: e37ce6e3a2dfad5395cdecf06178d64ec51b79f1
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415282"
---
# <a name="types-in-q"></a><span data-ttu-id="a90cc-103">Types en Q#</span><span class="sxs-lookup"><span data-stu-id="a90cc-103">Types in Q#</span></span>

<span data-ttu-id="a90cc-104">Cet article décrit le modèle de type Q # et la syntaxe permettant de spécifier et d’utiliser des types.</span><span class="sxs-lookup"><span data-stu-id="a90cc-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="a90cc-105">Pour plus d’informations sur la création et l’utilisation d’expressions de ces types, consultez [expressions de type](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="a90cc-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="a90cc-106">Nous remarquerons que Q # est un langage *fortement typé* , de sorte que l’utilisation prudente de ces types peut aider le compilateur à fournir des garanties fortes sur les programmes Q # au moment de la compilation.</span><span class="sxs-lookup"><span data-stu-id="a90cc-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="a90cc-107">Pour fournir les garanties les plus fortes possibles, les conversions entre les types dans Q # doivent être explicites à l’aide d’appels à des fonctions qui expriment cette conversion.</span><span class="sxs-lookup"><span data-stu-id="a90cc-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="a90cc-108">Q # fournit une variété de ces fonctions dans le cadre de l' <xref:microsoft.quantum.convert> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="a90cc-108">Q# provides a variety of such functions as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="a90cc-109">Les casts en types compatibles, en revanche, se produisent implicitement.</span><span class="sxs-lookup"><span data-stu-id="a90cc-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="a90cc-110">Q # fournit les deux types primitifs, qui sont utilisés directement, et diverses façons de produire de nouveaux types à partir d’autres types.</span><span class="sxs-lookup"><span data-stu-id="a90cc-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="a90cc-111">Nous décrivons chacun d’entre eux dans le reste de cet article.</span><span class="sxs-lookup"><span data-stu-id="a90cc-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="a90cc-112">Types primitifs</span><span class="sxs-lookup"><span data-stu-id="a90cc-112">Primitive Types</span></span>

<span data-ttu-id="a90cc-113">Le langage Q # fournit les *types primitifs*suivants, que vous pouvez utiliser directement dans les programmes Q #.</span><span class="sxs-lookup"><span data-stu-id="a90cc-113">The Q# language provides the following *primitive types*, all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="a90cc-114">Vous pouvez également utiliser ces types primitifs pour construire de nouveaux types.</span><span class="sxs-lookup"><span data-stu-id="a90cc-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="a90cc-115">Le `Int` type représente un entier signé 64 bits, par exemple,, `2` , `107` `-5` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="a90cc-116">Le `BigInt` type représente un entier signé de taille arbitraire, par exemple,,, `2L` `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="a90cc-117">Ce type est basé sur .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="a90cc-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="a90cc-118">entrer.</span><span class="sxs-lookup"><span data-stu-id="a90cc-118">type.</span></span>

- <span data-ttu-id="a90cc-119">Le `Double` type représente un nombre à virgule flottante double précision, par exemple,,, `0.0` `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="a90cc-120">Le `Bool` type représente une valeur booléenne de `true` ou `false` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="a90cc-121">Le `Range` type représente une séquence d’entiers, dénotée par `start..step..stop` , où le signalement de l’étape est facultatif.</span><span class="sxs-lookup"><span data-stu-id="a90cc-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="a90cc-122">Par exemple, `start .. stop` correspond à `start..1..stop` , et `1..2..7` représente la séquence $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="a90cc-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="a90cc-123">Le `String` type est une séquence de caractères Unicode qui est opaque pour l’utilisateur une fois créé.</span><span class="sxs-lookup"><span data-stu-id="a90cc-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="a90cc-124">Utilisez le `string` type pour signaler des messages à un hôte classique dans le cas d’une erreur ou d’un événement de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="a90cc-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="a90cc-125">Le `Unit` type ne peut avoir qu’une seule valeur, `()` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="a90cc-126">Utilisez ce type pour indiquer qu’une fonction ou une opération Q # ne retourne aucune information.</span><span class="sxs-lookup"><span data-stu-id="a90cc-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="a90cc-127">Le `Qubit` type représente un bit Quantum ou qubit.</span><span class="sxs-lookup"><span data-stu-id="a90cc-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="a90cc-128">`Qubit`les s sont opaques à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a90cc-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="a90cc-129">La seule opération possible avec eux, à l’exception de leur passage à une autre opération, consiste à tester l’identité (égalité).</span><span class="sxs-lookup"><span data-stu-id="a90cc-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="a90cc-130">Enfin, vous implémentez des actions sur `Qubit` s en appelant des instructions intrinsèques sur un processeur Quantum (ou un simulateur Quantum).</span><span class="sxs-lookup"><span data-stu-id="a90cc-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="a90cc-131">Le `Pauli` type représente l’un des quatre opérateurs Pauli à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="a90cc-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="a90cc-132">Utilisez ce type pour désigner l’opération de base pour les rotations et pour spécifier l’observable mesuré.</span><span class="sxs-lookup"><span data-stu-id="a90cc-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="a90cc-133">Il s’agit d’un type énuméré qui a quatre valeurs possibles : `PauliI` , `PauliX` , `PauliY` et `PauliZ` , qui sont des constantes de type `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="a90cc-134">Le `Result` type représente le résultat d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="a90cc-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="a90cc-135">Il s’agit d’un type énuméré avec deux valeurs possibles : `One` et `Zero` , qui sont des constantes de type `Result` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="a90cc-136">`Zero`indique que le eigenvalue + 1 a été mesuré ; `One`indique que le eigenvalue-1 a été mesuré.</span><span class="sxs-lookup"><span data-stu-id="a90cc-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="a90cc-137">Les constantes,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` et `Zero` sont tous des symboles réservés dans Q #.</span><span class="sxs-lookup"><span data-stu-id="a90cc-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="a90cc-138">Types de tableaux</span><span class="sxs-lookup"><span data-stu-id="a90cc-138">Array Types</span></span>

* <span data-ttu-id="a90cc-139">Pour tout type Q # valide, il existe un type qui représente un tableau de valeurs de ce type.</span><span class="sxs-lookup"><span data-stu-id="a90cc-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="a90cc-140">Par exemple, `Qubit[]` et `(Bool, Pauli)[]` représentent des tableaux de `Qubit` valeurs et de `(Bool, Pauli)` valeurs de Tuple.</span><span class="sxs-lookup"><span data-stu-id="a90cc-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="a90cc-141">Un tableau de tableaux est également valide.</span><span class="sxs-lookup"><span data-stu-id="a90cc-141">An array of arrays is also valid.</span></span> <span data-ttu-id="a90cc-142">En développant l’exemple précédent, un tableau de `(Bool, Pauli)` tableaux est indiqué `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="a90cc-143">Cet exemple, `(Bool, Pauli)[][]` , représente un tableau potentiellement irrégulier de tableaux et non un tableau rectangulaire à deux dimensions.</span><span class="sxs-lookup"><span data-stu-id="a90cc-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="a90cc-144">Q # ne prend pas en charge les tableaux multidimensionnels rectangulaires.</span><span class="sxs-lookup"><span data-stu-id="a90cc-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="a90cc-145">Une valeur de tableau peut être écrite dans le code source Q # en utilisant des crochets autour des éléments d’un tableau, comme dans `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="a90cc-146">Le type de base commun de tous les éléments du tableau détermine le type d’un littéral de tableau.</span><span class="sxs-lookup"><span data-stu-id="a90cc-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="a90cc-147">Par conséquent, la construction d’un tableau avec des éléments qui n’ont pas de type de base commun génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="a90cc-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="a90cc-148">Pour obtenir un exemple, consultez [tableaux de callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span><span class="sxs-lookup"><span data-stu-id="a90cc-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="a90cc-149">Une fois créés, les éléments d’un tableau ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="a90cc-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="a90cc-150">Pour construire un tableau modifié, utilisez les [instructions Update-and-réassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) ou les [expressions copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="a90cc-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="a90cc-151">Un tableau peut également être créé à partir de sa taille à l’aide du `new` mot clé :</span><span class="sxs-lookup"><span data-stu-id="a90cc-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="a90cc-152">Utilisez la fonction principale `Length` pour obtenir le nombre d’éléments d’un tableau sous la forme d’un `Int` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="a90cc-153">Les tableaux peuvent être en indice pour obtenir des éléments uniques ou de nouveaux tableaux contenant un sous-ensemble des éléments d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="a90cc-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="a90cc-154">Les indices de tableaux sont de base zéro et doivent être de type `Int` ou de type `Range` :</span><span class="sxs-lookup"><span data-stu-id="a90cc-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="a90cc-155">Types de tuples</span><span class="sxs-lookup"><span data-stu-id="a90cc-155">Tuple Types</span></span>

<span data-ttu-id="a90cc-156">Les tuples sont un concept puissant utilisé dans Q # pour regrouper des valeurs dans une valeur unique, ce qui facilite leur transmission.</span><span class="sxs-lookup"><span data-stu-id="a90cc-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="a90cc-157">En particulier, en utilisant la notation de tuple, vous pouvez exprimer que chaque opération et pouvant être appelée accepte exactement une entrée et retourne une seule sortie.</span><span class="sxs-lookup"><span data-stu-id="a90cc-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="a90cc-158">À partir de zéro, un ou plusieurs types différents `T0` , `T1` ,..., `Tn` , vous pouvez désigner un nouveau *type de tuple* comme `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="a90cc-159">Les types utilisés pour construire un nouveau type de tuple peuvent eux-mêmes être des tuples, comme dans `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="a90cc-160">Toutefois, cette imbrication est toujours finie, car les types de tuple ne peuvent en aucun cas contenir eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="a90cc-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="a90cc-161">Les valeurs du nouveau type de tuple sont des tuples formés par des séquences de valeurs de chaque type dans le tuple.</span><span class="sxs-lookup"><span data-stu-id="a90cc-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="a90cc-162">Par exemple, `(3, false)` est un tuple dont le type est le type de Tuple `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="a90cc-163">Il est possible de créer des tableaux de tuples, des tuples de tableaux, des tuples de sous-tuples, etc.</span><span class="sxs-lookup"><span data-stu-id="a90cc-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="a90cc-164">À partir de Q # 0,3, `Unit` est le nom du *type* du tuple vide ; `()` est utilisé pour la *valeur* du tuple vide.</span><span class="sxs-lookup"><span data-stu-id="a90cc-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="a90cc-165">Les instances de tuple sont immuables.</span><span class="sxs-lookup"><span data-stu-id="a90cc-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="a90cc-166">Q # ne fournit pas de mécanisme permettant de modifier le contenu d’un tuple une fois créé.</span><span class="sxs-lookup"><span data-stu-id="a90cc-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="a90cc-167">Équivalence de tuple de Singleton</span><span class="sxs-lookup"><span data-stu-id="a90cc-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="a90cc-168">Il est possible de créer un tuple (élément unique) Singleton `('T1)` , tel que `(5)` ou `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="a90cc-169">Toutefois, Q # traite un tuple Singleton comme équivalant à une valeur du type délimité.</span><span class="sxs-lookup"><span data-stu-id="a90cc-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="a90cc-170">Autrement dit, il n’existe aucune différence entre `5` et `(5)` , ou entre et `5` `(((5)))` , ou entre `(5, (6))` et `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="a90cc-171">Il est tout aussi valide que d’écrire, `(5)+3` car `5+3` les deux expressions ont la valeur `8` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="a90cc-172">Cette équivalence s’applique à tous les usages, y compris les affectations et les expressions.</span><span class="sxs-lookup"><span data-stu-id="a90cc-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="a90cc-173">À partir de toute expression, cette même expression entre parenthèses est une expression du même type.</span><span class="sxs-lookup"><span data-stu-id="a90cc-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="a90cc-174">Par exemple, `(7)` est une expression de type `Int` , `([1,2,3])` est une expression de type `Int[]` et `((1,2))` est une expression de type `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="a90cc-175">En particulier, cela signifie que vous pouvez afficher une opération ou une fonction dont le type de tuple d’entrée ou de sortie a un champ comme prenant un argument unique ou en retournant une valeur unique.</span><span class="sxs-lookup"><span data-stu-id="a90cc-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="a90cc-176">Nous faisons référence à cette propriété en tant qu' _équivalence de tuples Singleton_.</span><span class="sxs-lookup"><span data-stu-id="a90cc-176">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="a90cc-177">Types définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a90cc-177">User-Defined Types</span></span>

<span data-ttu-id="a90cc-178">Une déclaration de type défini par l’utilisateur se compose du mot clé `newtype` , suivi du nom du type défini par l’utilisateur, d’un `=` , d’une spécification de type valide et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="a90cc-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="a90cc-179">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a90cc-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="a90cc-180">Chaque fichier source Q # peut déclarer un nombre quelconque de types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a90cc-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="a90cc-181">Les noms de types doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms d’opération et de fonction.</span><span class="sxs-lookup"><span data-stu-id="a90cc-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="a90cc-182">Les types définis par l’utilisateur sont distincts, même si les types de base sont identiques.</span><span class="sxs-lookup"><span data-stu-id="a90cc-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="a90cc-183">En particulier, il n’y a pas de conversion automatique entre les valeurs de deux types définis par l’utilisateur, même si les types sous-jacents sont identiques.</span><span class="sxs-lookup"><span data-stu-id="a90cc-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="a90cc-184">Éléments nommés et anonymes</span><span class="sxs-lookup"><span data-stu-id="a90cc-184">Named vs. anonymous items</span></span>

<span data-ttu-id="a90cc-185">Un fichier Q # peut définir un nouveau type nommé contenant une valeur unique de n’importe quel type légal.</span><span class="sxs-lookup"><span data-stu-id="a90cc-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="a90cc-186">Pour tout type de Tuple `T` , vous pouvez déclarer un nouveau type défini par l’utilisateur qui est un sous-type de `T` avec l' `newtype` instruction.</span><span class="sxs-lookup"><span data-stu-id="a90cc-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="a90cc-187">Dans l' @"microsoft.quantum.math" espace de noms, par exemple, les nombres complexes sont définis comme un type défini par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="a90cc-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="a90cc-188">Cette instruction crée un nouveau type avec deux éléments anonymes de type `Double` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="a90cc-189">À part les éléments anonymes, les types définis par l’utilisateur prennent également en charge les *éléments nommés* à partir de Q # version 0,7 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="a90cc-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="a90cc-190">Par exemple, vous pouvez nommer les éléments en `Re` pour le double représentant la partie réelle d’un nombre complexe et `Im` pour la partie imaginaire :</span><span class="sxs-lookup"><span data-stu-id="a90cc-190">For example, you could name the items to `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="a90cc-191">L’attribution d’un nom à un élément dans un type défini par l’utilisateur n’implique pas que tous les éléments doivent être nommés-toute combinaison d’éléments nommés et sans nom est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a90cc-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="a90cc-192">En outre, les éléments internes peuvent également être nommés.</span><span class="sxs-lookup"><span data-stu-id="a90cc-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="a90cc-193">Le type `Nested` , tel que défini ci-dessous, a un type sous-jacent `(Double, (Int, String))` dont seul l’élément de type `Int` est nommé et tous les autres éléments sont anonymes.</span><span class="sxs-lookup"><span data-stu-id="a90cc-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="a90cc-194">Les éléments nommés présentent l’avantage de pouvoir accéder directement à l’aide de l' *opérateur d’accès* `::` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="a90cc-195">En plus de fournir des alias courts pour les types de tuple potentiellement compliqués, un avantage significatif de la définition de ces types est qu’ils peuvent documenter l’intention d’une valeur particulière.</span><span class="sxs-lookup"><span data-stu-id="a90cc-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="a90cc-196">En revenant à l’exemple de `Complex` , vous pouvez également définir des coordonnées polaires 2D comme type défini par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="a90cc-196">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="a90cc-197">Même si `Complex` et `Polar` les deux ont un type sous-jacent `(Double, Double)` , les deux types sont entièrement incompatibles dans Q #, ce qui réduit le risque d’appeler accidentellement une fonction mathématique complexe avec des coordonnées polaires, et vice versa.</span><span class="sxs-lookup"><span data-stu-id="a90cc-197">Even though both `Complex` and `Polar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="a90cc-198">Accéder aux éléments anonymes avec l’opérateur Unwrap</span><span class="sxs-lookup"><span data-stu-id="a90cc-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="a90cc-199">Pour accéder aux éléments anonymes, commencez par extraire la valeur encapsulée à l’aide de l’opérateur postfix `!` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="a90cc-200">Avec l’opérateur « Unwrap », `!` , vous pouvez extraire la valeur contenue dans un type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a90cc-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="a90cc-201">Le type d’une telle expression « Unwrap » est le type sous-jacent du type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a90cc-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="a90cc-202">Un opérateur Unwrap unique désencapsule une couche de renvoi à la ligne.</span><span class="sxs-lookup"><span data-stu-id="a90cc-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="a90cc-203">Utilisez plusieurs opérateurs de désencapsulage pour accéder à une valeur encapsuleuse.</span><span class="sxs-lookup"><span data-stu-id="a90cc-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="a90cc-204">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a90cc-204">For example:</span></span>

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

<span data-ttu-id="a90cc-205">Pour plus d’informations sur l’opérateur Unwrap, consultez [expressions de type dans Q #](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="a90cc-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="a90cc-206">Création de valeurs de types définis par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="a90cc-206">Creating values of user-defined types</span></span>

<span data-ttu-id="a90cc-207">Créez les valeurs d’un type défini par l’utilisateur en appelant le constructeur de type correspondant :</span><span class="sxs-lookup"><span data-stu-id="a90cc-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="a90cc-208">Vous pouvez également créer de nouvelles valeurs à partir de valeurs existantes à l’aide d' [expressions de copie et de mise à jour](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="a90cc-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="a90cc-209">Tout comme c’est le cas avec les tableaux, les expressions copy-and-Update copient toutes les valeurs d’élément de l’expression d’origine, à l’exception des éléments nommés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="a90cc-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="a90cc-210">Pour ces exceptions, les valeurs de ces éléments sont les valeurs définies sur le côté droit de l’expression.</span><span class="sxs-lookup"><span data-stu-id="a90cc-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="a90cc-211">Toutes les autres constructions de langage disponibles pour les éléments de tableau, par exemple les [instructions Update-and-réassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), existent pour les éléments nommés dans les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a90cc-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

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

* <span data-ttu-id="a90cc-212">Vous pouvez utiliser des types définis par l’utilisateur partout où vous utilisez d’autres types.</span><span class="sxs-lookup"><span data-stu-id="a90cc-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="a90cc-213">En particulier, il est possible de définir un tableau d’un type défini par l’utilisateur et d’inclure un type défini par l’utilisateur en tant qu’élément d’un type de Tuple.</span><span class="sxs-lookup"><span data-stu-id="a90cc-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="a90cc-214">Il n’est pas possible de créer des structures de types récursives.</span><span class="sxs-lookup"><span data-stu-id="a90cc-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="a90cc-215">Autrement dit, le type qui définit un type défini par l’utilisateur ne peut pas être un type de tuple qui comprend un élément du type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a90cc-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="a90cc-216">Plus généralement, les types définis par l’utilisateur ne peuvent pas avoir de dépendances cycliques les uns sur les autres. par conséquent, l’ensemble de définitions de type suivant n’est pas valide :</span><span class="sxs-lookup"><span data-stu-id="a90cc-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="a90cc-217">Types d’opérations et de fonctions</span><span class="sxs-lookup"><span data-stu-id="a90cc-217">Operation and Function Types</span></span>

<span data-ttu-id="a90cc-218">Selon les types `'Tinput` et `'Tresult` :</span><span class="sxs-lookup"><span data-stu-id="a90cc-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="a90cc-219">`('Tinput => 'Tresult)`est le type de base pour toute *opération*, par exemple `((Qubit, Pauli) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-219">`('Tinput => 'Tresult)` is the basic type for any *operation*, for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="a90cc-220">`('Tinput -> 'Tresult)`est le type de base pour n’importe quelle *fonction*, par exemple `(Int -> Int)` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-220">`('Tinput -> 'Tresult)` is the basic type for any *function*, for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="a90cc-221">Il s’agit de la *signature* de l’appelable.</span><span class="sxs-lookup"><span data-stu-id="a90cc-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="a90cc-222">Tous les Q # callables prennent une valeur unique comme entrée et retournent une valeur unique comme sortie.</span><span class="sxs-lookup"><span data-stu-id="a90cc-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="a90cc-223">Vous pouvez utiliser des tuples pour les valeurs d’entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="a90cc-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="a90cc-224">Callables qui n’ont pas de résultat, retournent `Unit` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="a90cc-225">Les callables qui n’ont aucune entrée prennent le tuple vide comme entrée.</span><span class="sxs-lookup"><span data-stu-id="a90cc-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="a90cc-226">Functors</span><span class="sxs-lookup"><span data-stu-id="a90cc-226">Functors</span></span>

<span data-ttu-id="a90cc-227">Les types de *fonction* sont complètement spécifiés par leur signature.</span><span class="sxs-lookup"><span data-stu-id="a90cc-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="a90cc-228">Par exemple, une fonction qui calcule le sinus d’un angle aurait le type `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="a90cc-229">Les *opérations* ont certaines caractéristiques supplémentaires qui sont exprimées dans le cadre du type d’opération.</span><span class="sxs-lookup"><span data-stu-id="a90cc-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="a90cc-230">Ces caractéristiques incluent des informations sur les *functors* pris en charge par l’opération.</span><span class="sxs-lookup"><span data-stu-id="a90cc-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="a90cc-231">Par exemple, si l’exécution de l’opération dépend de l’état d’autres qubits, elle doit prendre en charge le `Controlled` functor ; si l’opération a un inverse, elle doit prendre en charge `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="a90cc-231">For example, if the execution of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="a90cc-232">Cet article explique en quoi les functors altèrent la signature de l’opération.</span><span class="sxs-lookup"><span data-stu-id="a90cc-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="a90cc-233">Pour plus d’informations sur les functors et les opérations, consultez [Operations and Functions in Q #](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="a90cc-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="a90cc-234">Pour exiger la prise en charge de `Controlled` et/ou `Adjoint` de functor dans un type d’opération, vous devez ajouter une annotation indiquant les caractéristiques correspondantes.</span><span class="sxs-lookup"><span data-stu-id="a90cc-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="a90cc-235">L’annotation `is Ctl` (par exemple, `(Qubit => Unit is Ctl)` ) indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="a90cc-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="a90cc-236">Autrement dit, son exécution dépend de l’état d’un autre qubit ou qubits.</span><span class="sxs-lookup"><span data-stu-id="a90cc-236">That is, its execution relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="a90cc-237">De même, l’annotation `is Adj` indique que l’opération a un voisint, c’est-à-dire qu’elle peut être « inversée » de sorte que l’application consécutive d’une opération, puis son voisin à un État, laisse l’État inchangé.</span><span class="sxs-lookup"><span data-stu-id="a90cc-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="a90cc-238">Si vous souhaitez exiger qu’une opération de ce type prenne en charge à la fois le `Adjoint` et le `Controlled` functor, vous pouvez exprimer cela en tant que `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="a90cc-239">Par exemple, l’opération Pauli intégrée <xref:microsoft.quantum.intrinsic.x> a le type `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-239">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="a90cc-240">Un type d’opération qui ne prend en charge aucun functors est spécifié par son seul type d’entrée et de sortie, sans annotation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="a90cc-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="a90cc-241">Fonctions et opérations paramétrables</span><span class="sxs-lookup"><span data-stu-id="a90cc-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="a90cc-242">Les types pouvant être appelés peuvent contenir des *paramètres de type*.</span><span class="sxs-lookup"><span data-stu-id="a90cc-242">Callable types may contain *type parameters*.</span></span>
<span data-ttu-id="a90cc-243">Utilisez un symbole préfixé par un guillemet simple pour indiquer un paramètre de type ; par exemple, `'A` est un paramètre de type légal.</span><span class="sxs-lookup"><span data-stu-id="a90cc-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="a90cc-244">Pour plus d’informations et des détails sur la définition de callables paramétrables au type, consultez [opérations et fonctions dans Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span><span class="sxs-lookup"><span data-stu-id="a90cc-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="a90cc-245">Un paramètre de type peut apparaître plusieurs fois dans une même signature.</span><span class="sxs-lookup"><span data-stu-id="a90cc-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="a90cc-246">Par exemple, une fonction qui applique une autre fonction à chaque élément d’un tableau et retourne les résultats collectés possède la signature `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="a90cc-247">De même, une fonction qui retourne la composition de deux opérations possède la signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="a90cc-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="a90cc-248">Quand vous appelez un type paramétrable pouvant être appelé, tous les arguments qui ont le même paramètre de type doivent être du même type.</span><span class="sxs-lookup"><span data-stu-id="a90cc-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="a90cc-249">Q # ne fournit pas de mécanisme permettant de limiter les types possibles qu’un utilisateur peut remplacer par un paramètre de type.</span><span class="sxs-lookup"><span data-stu-id="a90cc-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a90cc-250">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="a90cc-250">Next steps</span></span>

<span data-ttu-id="a90cc-251">Maintenant que vous avez vu tous les types qui composent le langage Q #, consultez [expressions de type dans q #](xref:microsoft.quantum.guide.expressions) pour savoir comment créer et manipuler des expressions de ces différents types.</span><span class="sxs-lookup"><span data-stu-id="a90cc-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
