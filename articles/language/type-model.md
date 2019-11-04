---
title: 'Q # modèle de type | Microsoft Docs'
description: 'Q # modèle de type'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184744"
---
# <a name="the-type-model"></a><span data-ttu-id="179b7-103">Modèle de type</span><span class="sxs-lookup"><span data-stu-id="179b7-103">The Type Model</span></span>

<span data-ttu-id="179b7-104">Cette section présente le modèle Q # type et décrit la syntaxe permettant de spécifier et d’utiliser des types.</span><span class="sxs-lookup"><span data-stu-id="179b7-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="179b7-105">Nous remarquerons que Q # est un langage *fortement typé* , de sorte que l’utilisation prudente de ces types peut aider le compilateur à fournir des garanties fortes sur les programmes Q # au moment de la compilation.</span><span class="sxs-lookup"><span data-stu-id="179b7-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="179b7-106">Afin de fournir les garanties les plus fortes possibles, les conversions entre les types dans Q # doivent être explicites à l’aide d’appels à des fonctions qui expriment cette conversion.</span><span class="sxs-lookup"><span data-stu-id="179b7-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="179b7-107">Diverses fonctions de ce type sont fournies dans le cadre de l’espace de noms <xref:microsoft.quantum.convert>.</span><span class="sxs-lookup"><span data-stu-id="179b7-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="179b7-108">Les casts en types compatibles en revanche se produisent implicitement.</span><span class="sxs-lookup"><span data-stu-id="179b7-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="179b7-109">Q # fournit les deux types primitifs, qui peuvent être utilisés directement, ainsi que diverses façons de produire de nouveaux types à partir d’autres types.</span><span class="sxs-lookup"><span data-stu-id="179b7-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="179b7-110">Nous décrivons chacun d’entre eux dans le reste de cette section.</span><span class="sxs-lookup"><span data-stu-id="179b7-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="179b7-111">Types primitifs</span><span class="sxs-lookup"><span data-stu-id="179b7-111">Primitive Types</span></span>

<span data-ttu-id="179b7-112">Le langage Q # fournit plusieurs *types primitifs*, à partir desquels les autres types peuvent être construits :</span><span class="sxs-lookup"><span data-stu-id="179b7-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="179b7-113">Le type de `Int` représente un entier signé 64 bits, par exemple : `2`, `107`, `-5`.</span><span class="sxs-lookup"><span data-stu-id="179b7-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="179b7-114">Le type de `BigInt` représente un entier signé de taille arbitraire, par exemple `2L`, `107L``-5L`.</span><span class="sxs-lookup"><span data-stu-id="179b7-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="179b7-115">Ce type est basé sur le .NET <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="179b7-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="179b7-116">entrer.</span><span class="sxs-lookup"><span data-stu-id="179b7-116">type.</span></span>
- <span data-ttu-id="179b7-117">Le type de `Double` représente un nombre à virgule flottante double précision, par exemple : `0.0`, `-1.3`, `4e-7`.</span><span class="sxs-lookup"><span data-stu-id="179b7-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="179b7-118">Le type de `Bool` représente une valeur booléenne qui peut être `true` ou `false`.</span><span class="sxs-lookup"><span data-stu-id="179b7-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="179b7-119">Le type de `Qubit` représente un bit Quantum ou qubit.</span><span class="sxs-lookup"><span data-stu-id="179b7-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="179b7-120">`Qubit`s sont opaques à l’utilisateur ; la seule opération possible avec eux, à l’exception de leur passage à une autre opération, consiste à tester l’identité (égalité).</span><span class="sxs-lookup"><span data-stu-id="179b7-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="179b7-121">Au final, les actions sur `Qubit`s sont implémentées en appelant des instructions intrinsèques sur un processeur Quantum (ou une simulation de celle-ci).</span><span class="sxs-lookup"><span data-stu-id="179b7-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="179b7-122">Le type de `Pauli` représente l’un des quatre opérateurs Pauli à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="179b7-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="179b7-123">Ce type est utilisé pour désigner l’opération de base pour les rotations et pour spécifier l’observable en cours de mesure.</span><span class="sxs-lookup"><span data-stu-id="179b7-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="179b7-124">Il s’agit d’un type énuméré qui a quatre valeurs possibles : `PauliI`, `PauliX`, `PauliY`et `PauliZ`, qui sont des constantes de type `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="179b7-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="179b7-125">Le type de `Result` représente le résultat d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="179b7-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="179b7-126">Il s’agit d’un type énuméré avec deux valeurs possibles : `One` et `Zero`, qui sont des constantes de type `Result`.</span><span class="sxs-lookup"><span data-stu-id="179b7-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="179b7-127">`Zero` indique que le eigenvalue + 1 a été mesuré ; `One` indique-1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="179b7-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="179b7-128">Le type de `Range` représente une séquence d’entiers, dénotée par `start..step..stop`, où l’étape est des options.</span><span class="sxs-lookup"><span data-stu-id="179b7-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="179b7-129">Autrement dit `start .. stop` correspond à `start..1..stop`et, par exemple, `1..2..7` représente la séquence $\{1, 3, 5, 7\}$.</span><span class="sxs-lookup"><span data-stu-id="179b7-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="179b7-130">Le type de `String` est une séquence de caractères Unicode qui est opaque pour l’utilisateur une fois créé.</span><span class="sxs-lookup"><span data-stu-id="179b7-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="179b7-131">Ce type est utilisé pour signaler des messages à un hôte classique dans le cas d’une erreur ou d’un événement de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="179b7-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="179b7-132">Le type de `Unit` est le type qui autorise une seule valeur `()`.</span><span class="sxs-lookup"><span data-stu-id="179b7-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="179b7-133">Ce type est utilisé pour indiquer que la fonction ou l’opération Q # ne retourne aucune information.</span><span class="sxs-lookup"><span data-stu-id="179b7-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="179b7-134">Les constantes `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`et `Zero` sont tous des symboles réservés dans Q #.</span><span class="sxs-lookup"><span data-stu-id="179b7-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="179b7-135">Types tableau</span><span class="sxs-lookup"><span data-stu-id="179b7-135">Array Types</span></span>

<span data-ttu-id="179b7-136">Compte tenu des `'T`de type Q # valides, il existe un type qui représente un tableau de valeurs de type `'T`.</span><span class="sxs-lookup"><span data-stu-id="179b7-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="179b7-137">Ce type de tableau est représenté sous la forme `'T[]`; par exemple, `Qubit[]` ou `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="179b7-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="179b7-138">Par exemple, une collection d’entiers est dénotée `Int[]`, alors qu’un tableau de tableaux de valeurs `(Bool, Pauli)` est indiqué `(Bool, Pauli)[][]`.</span><span class="sxs-lookup"><span data-stu-id="179b7-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="179b7-139">Dans le deuxième exemple, Notez qu’il s’agit d’un tableau potentiellement en escalier des tableaux, et non d’un tableau rectangulaire à deux dimensions.</span><span class="sxs-lookup"><span data-stu-id="179b7-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="179b7-140">Q # ne prend pas en charge les tableaux multidimensionnels rectangulaires.</span><span class="sxs-lookup"><span data-stu-id="179b7-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="179b7-141">Une valeur de tableau peut être écrite dans le code source Q # en utilisant des crochets autour des éléments d’un tableau, comme dans `[PauliI, PauliX, PauliY, PauliZ]`.</span><span class="sxs-lookup"><span data-stu-id="179b7-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="179b7-142">Le type d’un littéral de tableau est déterminé par le type de base commun de tous les éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="179b7-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="179b7-143">Les éléments d’un tableau ne peuvent pas être modifiés une fois le tableau créé.</span><span class="sxs-lookup"><span data-stu-id="179b7-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="179b7-144">Les instructions Update-and-Assign et/ou copy-and-Update peuvent être utilisées pour construire un tableau modifié.</span><span class="sxs-lookup"><span data-stu-id="179b7-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="179b7-145">Un tableau peut également être créé à partir de sa taille à l’aide du mot clé `new` :</span><span class="sxs-lookup"><span data-stu-id="179b7-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="179b7-146">Dans les deux cas, une fois qu’un tableau a été construit, la fonction principale `Length` peut être utilisée pour obtenir le nombre d’éléments en tant que `Int`.</span><span class="sxs-lookup"><span data-stu-id="179b7-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="179b7-147">Les tableaux peuvent être sous-scriptés à l’aide de crochets, avec des indices de type `Int` ou `Range`pour obtenir des éléments uniques ou de nouveaux tableaux contenant un sous-ensemble des éléments d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="179b7-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="179b7-148">Les indices de tableaux sont de base zéro :</span><span class="sxs-lookup"><span data-stu-id="179b7-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="179b7-149">Types de tuples</span><span class="sxs-lookup"><span data-stu-id="179b7-149">Tuple Types</span></span>

<span data-ttu-id="179b7-150">À partir de zéro, un ou plusieurs types différents `T0`, `T1`,... `Tn`, nous pouvons désigner un nouveau *type de tuple* comme `(T0, T1, ..., Tn)`.</span><span class="sxs-lookup"><span data-stu-id="179b7-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="179b7-151">Les types utilisés pour construire un nouveau type de tuple peuvent eux-mêmes être des tuples, comme dans `(Int, (Qubit, Qubit))`.</span><span class="sxs-lookup"><span data-stu-id="179b7-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="179b7-152">Toutefois, cette imbrication est toujours finie, car les types de tuple ne peuvent en aucun cas contenir eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="179b7-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="179b7-153">Les valeurs du nouveau type de tuple sont des tuples formés par des séquences de valeurs de chaque type dans le tuple.</span><span class="sxs-lookup"><span data-stu-id="179b7-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="179b7-154">Par exemple, `(3, false)` est un tuple dont le type est le type de tuple `(Int, Bool)`.</span><span class="sxs-lookup"><span data-stu-id="179b7-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="179b7-155">Il est possible de créer des tableaux de tuples, des tuples de tableaux, des tuples de sous-tuples, etc.</span><span class="sxs-lookup"><span data-stu-id="179b7-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="179b7-156">À partir de Q # 0,3, `Unit` est le nom du *type* du tuple vide ; `()` est utilisé pour la *valeur*de tuple vide.</span><span class="sxs-lookup"><span data-stu-id="179b7-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="179b7-157">Les instances de tuple sont immuables.</span><span class="sxs-lookup"><span data-stu-id="179b7-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="179b7-158">Q # ne fournit pas de mécanisme permettant de modifier le contenu d’un tuple une fois créé.</span><span class="sxs-lookup"><span data-stu-id="179b7-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="179b7-159">Les tuples sont un concept puissant utilisé dans Q # pour regrouper des valeurs dans une valeur unique, ce qui facilite leur transmission.</span><span class="sxs-lookup"><span data-stu-id="179b7-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="179b7-160">En particulier, à l’aide de la notation de tuple, nous pouvons exprimer que chaque opération et Callable prend exactement une entrée et retourne une seule sortie.</span><span class="sxs-lookup"><span data-stu-id="179b7-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="179b7-161">Équivalence de tuple de Singleton</span><span class="sxs-lookup"><span data-stu-id="179b7-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="179b7-162">Il est possible de créer un tuple (élément unique) Singleton, `('T1)`, tel que `(5)` ou `([1,2,3])`.</span><span class="sxs-lookup"><span data-stu-id="179b7-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="179b7-163">Toutefois, Q # traite un tuple Singleton comme complètement équivalent à une valeur du type délimité.</span><span class="sxs-lookup"><span data-stu-id="179b7-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="179b7-164">Autrement dit, il n’y a aucune différence entre `5` et `(5)`, ou entre `5` et `(((5)))`, ou entre `(5, (6))` et `(5, 6)`.</span><span class="sxs-lookup"><span data-stu-id="179b7-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="179b7-165">Cette équivalence s’applique à tous les usages, y compris les affectations et les expressions.</span><span class="sxs-lookup"><span data-stu-id="179b7-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="179b7-166">Elle est tout aussi valide pour écrire des `(5)+3` en tant que pour écrire des `5+3`, et les deux expressions prennent la valeur `8`.</span><span class="sxs-lookup"><span data-stu-id="179b7-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="179b7-167">En particulier, cela signifie qu’une opération ou une fonction dont le type de tuple d’entrée ou de sortie a un champ peut être considérée comme prendre un seul argument ou retourner une valeur unique.</span><span class="sxs-lookup"><span data-stu-id="179b7-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="179b7-168">Nous faisons référence à cette propriété en tant qu' _équivalence de tuples Singleton_.</span><span class="sxs-lookup"><span data-stu-id="179b7-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="179b7-169">Types définis par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="179b7-169">User-Defined Types</span></span>

<span data-ttu-id="179b7-170">Un fichier Q # peut définir un nouveau type nommé contenant une valeur unique de n’importe quel type légal.</span><span class="sxs-lookup"><span data-stu-id="179b7-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="179b7-171">Pour tout type de tuple `T`, nous pouvons déclarer un nouveau type défini par l’utilisateur qui est un sous-type de `T` avec l’instruction `newtype`.</span><span class="sxs-lookup"><span data-stu-id="179b7-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="179b7-172">Dans l’espace de noms @"microsoft.quantum.canon", par exemple, les nombres complexes sont définis comme un type défini par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="179b7-172">In the @"microsoft.quantum.canon" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="179b7-173">Cette instruction crée un nouveau type avec deux éléments anonymes de type `Double`.</span><span class="sxs-lookup"><span data-stu-id="179b7-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="179b7-174">Outre les éléments anonymes, les types définis par l’utilisateur prennent également en charge les éléments nommés comme Q # version 0,7 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="179b7-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="179b7-175">Par exemple, nous aurions pu nommer le `Re` to items pour le double représentant la partie réelle d’un nombre complexe et `Im` pour la partie imaginaire :</span><span class="sxs-lookup"><span data-stu-id="179b7-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="179b7-176">L’attribution d’un nom à un élément dans un type défini par l’utilisateur n’implique pas que tous les éléments doivent être nommés-toute combinaison d’éléments nommés et sans nom est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="179b7-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="179b7-177">En outre, les éléments internes peuvent également être nommés.</span><span class="sxs-lookup"><span data-stu-id="179b7-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="179b7-178">Le type `Nested` comme indiqué ci-dessous, par exemple, a un type sous-jacent `(Double, (Int, String))`dont seul l’élément de type `Int` est nommé et tous les autres éléments sont anonymes.</span><span class="sxs-lookup"><span data-stu-id="179b7-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="179b7-179">Les éléments nommés présentent l’avantage de pouvoir être accessibles directement par le biais de l’opérateur d’accès `::`.</span><span class="sxs-lookup"><span data-stu-id="179b7-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="179b7-180">Pour pouvoir accéder à des éléments anonymes en revanche, la valeur encapsulée doit d’abord être extraite à l’aide de l’opérateur postfix `!`.</span><span class="sxs-lookup"><span data-stu-id="179b7-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="179b7-181">L’opérateur « Unwrap », `!`, permet d’extraire la valeur contenue dans un type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="179b7-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="179b7-182">Le type d’une telle expression « Unwrap » est le type sous-jacent du type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="179b7-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="179b7-183">L’opérateur Unwrap désencapsule une seule couche de renvoi à la ligne.</span><span class="sxs-lookup"><span data-stu-id="179b7-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="179b7-184">Plusieurs opérateurs Unwrap peuvent être utilisés pour accéder à une valeur encapsuleuse.</span><span class="sxs-lookup"><span data-stu-id="179b7-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="179b7-185">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="179b7-185">For instance:</span></span>

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

<span data-ttu-id="179b7-186">Pour plus d’informations, consultez la section sur les [expressions de désencapsulation](xref:microsoft.quantum.language.expressions#unwrap-expressions) et la [priorité des opérateurs](xref:microsoft.quantum.language.expressions#operator-precedence) .</span><span class="sxs-lookup"><span data-stu-id="179b7-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="179b7-187">Les valeurs d’un type défini par l’utilisateur peuvent être créées en appelant le constructeur de type correspondant :</span><span class="sxs-lookup"><span data-stu-id="179b7-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="179b7-188">Vous pouvez également créer de nouvelles valeurs à partir de valeurs existantes à l’aide d' [expressions de copie et de mise à jour](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="179b7-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="179b7-189">Comme pour les tableaux, ces expressions copient toutes les valeurs d’élément de l’expression d’origine, à l’exception des éléments nommés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="179b7-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="179b7-190">Pour ces valeurs, elles sont définies à celles définies sur le côté droit de l’expression.</span><span class="sxs-lookup"><span data-stu-id="179b7-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="179b7-191">Toutes les autres constructions de langage, comme par exemple les [instructions Update-and-Assign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), qui sont disponibles pour les éléments de tableau existent pour les éléments nommés dans les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="179b7-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="179b7-192">Les types définis par l’utilisateur peuvent être utilisés partout où un autre type peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="179b7-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="179b7-193">En particulier, il est possible de définir un tableau d’un type défini par l’utilisateur et d’inclure un type défini par l’utilisateur en tant qu’élément d’un type de Tuple.</span><span class="sxs-lookup"><span data-stu-id="179b7-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="179b7-194">Il n’est pas possible de créer des structures de types récursives.</span><span class="sxs-lookup"><span data-stu-id="179b7-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="179b7-195">Autrement dit, le type qui définit un type défini par l’utilisateur ne peut pas être un type de tuple qui comprend un élément du type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="179b7-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="179b7-196">Plus généralement, les types définis par l’utilisateur ne peuvent pas avoir de dépendances cycliques les uns sur les autres. par conséquent, l’ensemble de définitions de type suivant serait illégal :</span><span class="sxs-lookup"><span data-stu-id="179b7-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="179b7-197">En plus de fournir des alias courts pour les types de tuple potentiellement compliqués, l’un des avantages significatifs de la définition de ces types est qu’ils peuvent documenter l’intention d’une valeur particulière.</span><span class="sxs-lookup"><span data-stu-id="179b7-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="179b7-198">En revenant à l’exemple de `Complex`, il est possible d’avoir également défini des coordonnées polaires 2D comme type défini par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="179b7-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="179b7-199">Même si les deux `Complex` et `Polar` ont tous deux un type sous-jacent `(Double, Double)`, les deux types sont entièrement incompatibles dans Q #, ce qui réduit le risque d’appeler accidentellement une fonction mathématique complexe avec des coordonnées polaires, et vice versa.</span><span class="sxs-lookup"><span data-stu-id="179b7-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="179b7-200">De cette façon, les types définis par l’utilisateur ont un rôle similaire à F# celui des enregistrements dans, par exemple.</span><span class="sxs-lookup"><span data-stu-id="179b7-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="179b7-201">Types d’opérations et de fonctions</span><span class="sxs-lookup"><span data-stu-id="179b7-201">Operation and Function Types</span></span>

<span data-ttu-id="179b7-202">Une _opération_ Q # est une sous-routine Quantum.</span><span class="sxs-lookup"><span data-stu-id="179b7-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="179b7-203">Autrement dit, il s’agit d’une routine pouvant être appelée qui contient des opérations de Quantum.</span><span class="sxs-lookup"><span data-stu-id="179b7-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="179b7-204">Une _fonction_ Q # est une sous-routine classique utilisée dans un algorithme Quantum.</span><span class="sxs-lookup"><span data-stu-id="179b7-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="179b7-205">Elle peut contenir du code classique, mais aucune opération Quantum.</span><span class="sxs-lookup"><span data-stu-id="179b7-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="179b7-206">Plus précisément, les fonctions ne peuvent pas allouer ou emprunter des qubits, ni appeler des opérations.</span><span class="sxs-lookup"><span data-stu-id="179b7-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="179b7-207">Toutefois, il est possible de leur transmettre des opérations ou des qubits de traitement.</span><span class="sxs-lookup"><span data-stu-id="179b7-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="179b7-208">Les fonctions sont donc entièrement déterministes dans le sens où l’appel de ces mêmes arguments produira toujours le même résultat.</span><span class="sxs-lookup"><span data-stu-id="179b7-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="179b7-209">Ensemble, les opérations et les fonctions sont appelées _callables_.</span><span class="sxs-lookup"><span data-stu-id="179b7-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="179b7-210">Vous pouvez voir quelques [exemples](#examples) ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="179b7-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="179b7-211">Tous les Q # callables sont considérés comme une valeur unique comme entrée et retournent une valeur unique comme sortie.</span><span class="sxs-lookup"><span data-stu-id="179b7-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="179b7-212">Les valeurs d’entrée et de sortie peuvent être des tuples.</span><span class="sxs-lookup"><span data-stu-id="179b7-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="179b7-213">Callables qui n’ont pas de résultat de retour `Unit`.</span><span class="sxs-lookup"><span data-stu-id="179b7-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="179b7-214">Les callables qui n’ont aucune entrée prennent le tuple vide comme entrée.</span><span class="sxs-lookup"><span data-stu-id="179b7-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="179b7-215">Le type de base pour tout appelable est écrit sous la forme `('Tinput => 'Tresult)` ou `('Tinput -> 'Tresult)`, où `'Tinput` et `'Tresult` sont des types.</span><span class="sxs-lookup"><span data-stu-id="179b7-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="179b7-216">La première forme, avec `=>`, est utilisée pour les opérations ; deuxième forme, avec `->`, pour les fonctions.</span><span class="sxs-lookup"><span data-stu-id="179b7-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="179b7-217">Par exemple, `((Qubit, Pauli) => Result)` représente la signature d’une opération de mesure qubit unique.</span><span class="sxs-lookup"><span data-stu-id="179b7-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="179b7-218">Les types de fonction sont complètement spécifiés par leur signature.</span><span class="sxs-lookup"><span data-stu-id="179b7-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="179b7-219">Par exemple, une fonction qui calcule le sinus d’un angle aurait un type `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="179b7-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="179b7-220">Les opérations, mais pas les fonctions, ont certaines _caractéristiques_ supplémentaires qui sont exprimées dans le cadre du type d’opération.</span><span class="sxs-lookup"><span data-stu-id="179b7-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="179b7-221">Ces caractéristiques incluent des informations sur les functors pris en charge par l’opération.</span><span class="sxs-lookup"><span data-stu-id="179b7-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="179b7-222">Les functors sont des méta-opérations qui génèrent une spécialisation d’une opération de base. consultez les [functors](#functors), ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="179b7-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="179b7-223">Les types d’opérations sont spécifiés par leur type d’entrée, leur type de sortie et leurs caractéristiques.</span><span class="sxs-lookup"><span data-stu-id="179b7-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="179b7-224">Pour exiger la prise en charge des `Controlled` et/ou `Adjoint` functor dans un type d’opération, nous devons ajouter une annotation indiquant les caractéristiques correspondantes.</span><span class="sxs-lookup"><span data-stu-id="179b7-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="179b7-225">Une `is Ctl` d’annotation, par exemple, indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="179b7-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="179b7-226">Si nous souhaitons exiger qu’une opération de ce type prenne en charge les `Adjoint` et `Controlled` functor, nous pouvons exprimer cela comme `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="179b7-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="179b7-227">Les caractéristiques d’opération utilisées `Adj` et `Ctl` strictement parlant sont deux ensembles prédéfinis d’étiquettes, où chaque étiquette indique une caractéristique d’opération particulière comme par exemple, la prise en charge d’un functor particulier.</span><span class="sxs-lookup"><span data-stu-id="179b7-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="179b7-228">Par conséquent, `+` est utilisé pour indiquer l’Union de ces deux jeux, et `*` est utilisé pour indiquer l’intersection, c’est-à-dire les étiquettes qui sont communes aux deux ensembles.</span><span class="sxs-lookup"><span data-stu-id="179b7-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="179b7-229">Par exemple, l’opération de `X` Pauli a le type `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="179b7-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="179b7-230">Un type d’opération qui ne prend en charge aucun functors est spécifié par son seul type d’entrée et de sortie, sans annotation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="179b7-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="179b7-231">Fonctions et opérations paramétrables</span><span class="sxs-lookup"><span data-stu-id="179b7-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="179b7-232">Les types pouvant être appelés peuvent contenir des paramètres de type.</span><span class="sxs-lookup"><span data-stu-id="179b7-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="179b7-233">Les paramètres de type sont indiqués par un symbole préfixé par un guillemet simple ; par exemple, `'A` est un paramètre de type légal.</span><span class="sxs-lookup"><span data-stu-id="179b7-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="179b7-234">Un paramètre de type peut apparaître plusieurs fois dans une même signature.</span><span class="sxs-lookup"><span data-stu-id="179b7-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="179b7-235">Par exemple, une fonction qui applique une autre fonction à chaque élément d’un tableau et retourne les résultats collectés aurait une signature `(('A[], 'A->'A) -> 'A[])`.</span><span class="sxs-lookup"><span data-stu-id="179b7-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="179b7-236">De même, une fonction qui retourne la composition de deux opérations peut avoir une signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span><span class="sxs-lookup"><span data-stu-id="179b7-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="179b7-237">Lors de l’appel d’un pouvant être appelé par un type paramétrable, tous les arguments qui ont le même paramètre de type doivent être du même type.</span><span class="sxs-lookup"><span data-stu-id="179b7-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="179b7-238">Q # ne fournit pas de mécanisme permettant de limiter les types possibles qui peuvent être remplacés par un paramètre de type.</span><span class="sxs-lookup"><span data-stu-id="179b7-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="179b7-239">Compatibilité de type</span><span class="sxs-lookup"><span data-stu-id="179b7-239">Type Compatibility</span></span>

<span data-ttu-id="179b7-240">Une opération avec des functors supplémentaires pris en charge peut être utilisée partout où une opération avec moins d’functors, mais la même signature est attendue.</span><span class="sxs-lookup"><span data-stu-id="179b7-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="179b7-241">Par exemple, une opération de type `(Qubit => Unit is Adj)` peut être utilisée partout où une opération de type `(Qubit => Unit)` est attendue.</span><span class="sxs-lookup"><span data-stu-id="179b7-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="179b7-242">Q # est covariant en ce qui concerne les types de retour pouvant être appelés : un pouvant être appelé qui retourne un type `'A` est compatible avec un pouvant être appelé avec le même type d’entrée et un type de résultat qui `'A` est compatible avec.</span><span class="sxs-lookup"><span data-stu-id="179b7-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="179b7-243">Q # est contravariant en ce qui concerne les types d’entrée : un pouvant être appelé qui accepte un type `'A` comme entrée est compatible avec un pouvant être appelé avec le même type de résultat et un type d’entrée compatible avec `'A`.</span><span class="sxs-lookup"><span data-stu-id="179b7-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="179b7-244">Autrement dit, étant donné les définitions suivantes :</span><span class="sxs-lookup"><span data-stu-id="179b7-244">That is, given the following definitions:</span></span>

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="179b7-245">les conditions suivantes sont vraies :</span><span class="sxs-lookup"><span data-stu-id="179b7-245">the following are true:</span></span>

- <span data-ttu-id="179b7-246">L’opération `ConjugateInvertibleWith` peut être appelée avec un argument `inner` de `Invertible` ou `Unitary`.</span><span class="sxs-lookup"><span data-stu-id="179b7-246">The operation `ConjugateInvertibleWith` may be invoked with an `inner` argument of either `Invertible` or `Unitary`.</span></span>
- <span data-ttu-id="179b7-247">L’opération `ConjugateUnitaryWith` peut être appelée avec un argument `inner` de `Unitary`, mais pas `Invertible`.</span><span class="sxs-lookup"><span data-stu-id="179b7-247">The operation `ConjugateUnitaryWith` may be invoked with an `inner` argument of `Unitary`, but not `Invertible`.</span></span>
- <span data-ttu-id="179b7-248">Une valeur de type `(Qubit[] => Unit is Adj + Ctl)` peut être retournée à partir de `ConjugateInvertibleWith`.</span><span class="sxs-lookup"><span data-stu-id="179b7-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertibleWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="179b7-249">Q # 0,3 introduit une différence significative dans le comportement des types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="179b7-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="179b7-250">Les types définis par l’utilisateur sont traités comme une version encapsulée du type sous-jacent, plutôt qu’en tant que sous-type.</span><span class="sxs-lookup"><span data-stu-id="179b7-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="179b7-251">Cela signifie qu’une valeur d’un type défini par l’utilisateur n’est pas utilisable quand une valeur du type sous-jacent est attendue.</span><span class="sxs-lookup"><span data-stu-id="179b7-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="179b7-252">Functors</span><span class="sxs-lookup"><span data-stu-id="179b7-252">Functors</span></span>

<span data-ttu-id="179b7-253">Un functor dans Q # est une fabrique qui définit une nouvelle opération à partir d’une autre opération.</span><span class="sxs-lookup"><span data-stu-id="179b7-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="179b7-254">Les functors ont accès à l’implémentation de l’opération de base lors de la définition de l’implémentation de la nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="179b7-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="179b7-255">Ainsi, les functors peuvent exécuter des fonctions plus complexes que les fonctions de niveau supérieur traditionnelles.</span><span class="sxs-lookup"><span data-stu-id="179b7-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="179b7-256">Les functors n’ont pas de représentation dans le système Q # type.</span><span class="sxs-lookup"><span data-stu-id="179b7-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="179b7-257">Il n’est donc actuellement pas possible de les lier à une variable ou de les passer comme arguments.</span><span class="sxs-lookup"><span data-stu-id="179b7-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="179b7-258">Un functor est utilisé en l’appliquant à une opération, en retournant une nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="179b7-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="179b7-259">Par exemple, l’opération qui résulte de l’application de l' `Adjoint` functor à l’opération `Y` est écrite en tant que `Adjoint Y`.</span><span class="sxs-lookup"><span data-stu-id="179b7-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="179b7-260">La nouvelle opération peut ensuite être appelée comme toute autre opération.</span><span class="sxs-lookup"><span data-stu-id="179b7-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="179b7-261">Ainsi, `Adjoint Y(q1)` applique le functor joint à l’opération `Y` pour générer une nouvelle opération et applique cette nouvelle opération à `q1`.</span><span class="sxs-lookup"><span data-stu-id="179b7-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="179b7-262">De même, `Controlled X(controls, target)` applique la functor contrôlée à l’opération `X` pour générer une nouvelle opération et applique cette nouvelle opération à `controls` et `target`.</span><span class="sxs-lookup"><span data-stu-id="179b7-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="179b7-263">Les deux functors standard de Q # sont `Adjoint` et `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="179b7-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="179b7-264">Voisin</span><span class="sxs-lookup"><span data-stu-id="179b7-264">Adjoint</span></span>

<span data-ttu-id="179b7-265">Dans Quantum Computing, le voisin d’une opération est la complexe conjugué de l’opération.</span><span class="sxs-lookup"><span data-stu-id="179b7-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="179b7-266">Pour les opérations qui implémentent un opérateur unitaire, le voisin est l’inverse de l’opération.</span><span class="sxs-lookup"><span data-stu-id="179b7-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="179b7-267">Pour une opération simple qui appelle simplement une séquence d’autres opérations unitaires sur un ensemble de qubits, le voisint peut être calculé en appliquant les adjoints des sous-opérations sur le même qubits, dans l’ordre inverse.</span><span class="sxs-lookup"><span data-stu-id="179b7-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="179b7-268">En fonction d’une expression d’opération, une nouvelle expression d’opération peut être formée à l’aide de l' `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="179b7-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="179b7-269">Par exemple, `Adjoint QFT` désigne le voisin du `QFT` opération.</span><span class="sxs-lookup"><span data-stu-id="179b7-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="179b7-270">La nouvelle opération a la même signature et le même type que l’opération de base.</span><span class="sxs-lookup"><span data-stu-id="179b7-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="179b7-271">En particulier, la nouvelle opération autorise également `Adjoint`et autorise `Controlled` si et uniquement si l’opération de base a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="179b7-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="179b7-272">Le functor de l’Contigut est son propre inverse ; autrement dit, `Adjoint Adjoint Op` est toujours identique à `Op`.</span><span class="sxs-lookup"><span data-stu-id="179b7-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="179b7-273">Contrôl</span><span class="sxs-lookup"><span data-stu-id="179b7-273">Controlled</span></span>

<span data-ttu-id="179b7-274">La version contrôlée d’une opération est une nouvelle opération qui applique efficacement l’opération de base uniquement si tous les qubits de contrôle sont dans un état spécifié.</span><span class="sxs-lookup"><span data-stu-id="179b7-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="179b7-275">Si le contrôle qubits est en superposition, l’opération de base est appliquée de manière cohérente à la partie appropriée de la superposition.</span><span class="sxs-lookup"><span data-stu-id="179b7-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="179b7-276">Ainsi, les opérations contrôlées sont souvent utilisées pour générer l’enchevêtrement.</span><span class="sxs-lookup"><span data-stu-id="179b7-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="179b7-277">Dans Q #, les versions contrôlées prennent toujours un tableau de qubits de contrôle, et l’état spécifié est toujours pour tous les qubits de contrôle dans l’état de `One` de calcul (`PauliZ`), $ \ket{1}$.</span><span class="sxs-lookup"><span data-stu-id="179b7-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="179b7-278">Le contrôle basé sur d’autres États peut être obtenu en appliquant l’opération unitaire appropriée à l’qubits de contrôle avant l’opération contrôlée, puis en appliquant les inversions de l’opération unitaire après l’opération contrôlée.</span><span class="sxs-lookup"><span data-stu-id="179b7-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="179b7-279">Par exemple, l’application d’une opération de `X` à un contrôle qubit avant et après une opération contrôlée entraînera le contrôle de l’opération sur l’État `Zero` ($ \ket{0}$) pour ce qubit ; l’application d’une `H` opération avant et après contrôle l’état de la `One` `PauliX`, c’est-à-dire-1 eigenvalue de Pauli X, $ \ket{-} \mathrel{ : =} (\ket{0}-\ket{1})/\sqrt{2}$ au lieu de l’État `PauliZ` `One`.</span><span class="sxs-lookup"><span data-stu-id="179b7-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="179b7-280">En fonction d’une expression d’opération, une nouvelle expression d’opération peut être formée à l’aide de l' `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="179b7-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="179b7-281">La signature de la nouvelle opération est basée sur la signature de l’opération d’origine.</span><span class="sxs-lookup"><span data-stu-id="179b7-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="179b7-282">Le type de résultat est le même, mais le type d’entrée est un double Tuple avec un tableau qubit qui contient les qubit de contrôle comme premier élément et les arguments de l’opération d’origine comme second élément.</span><span class="sxs-lookup"><span data-stu-id="179b7-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="179b7-283">La nouvelle opération prend en charge `Controlled`et prendra en charge `Adjoint` si et uniquement si l’opération d’origine a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="179b7-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="179b7-284">Si l’opération d’origine n’a pris qu’un seul argument, l’équivalence du tuple de Singleton sera alors lue ici.</span><span class="sxs-lookup"><span data-stu-id="179b7-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="179b7-285">Par exemple, `Controlled X` est la version contrôlée de l’opération `X`.</span><span class="sxs-lookup"><span data-stu-id="179b7-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="179b7-286">`X` a le type `(Qubit => Unit is Adj + Ctl)`, donc `Controlled X` a le type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; en raison de l’équivalence des tuples Singleton, il est identique à `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="179b7-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="179b7-287">Si l’opération de base a pris plusieurs arguments, n’oubliez pas de placer les arguments correspondants de la version contrôlée de l’opération entre parenthèses pour les convertir en Tuple.</span><span class="sxs-lookup"><span data-stu-id="179b7-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="179b7-288">Par exemple, `Controlled Rz` est la version contrôlée de l’opération `Rz`.</span><span class="sxs-lookup"><span data-stu-id="179b7-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="179b7-289">`Rz` est de type `((Double, Qubit) => Unit is Adj + Ctl)`, `Controlled Rz` est donc de type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="179b7-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="179b7-290">Par conséquent, `Controlled Rz(controls, (0.1, target))` serait un appel valide de `Controlled Rz` (Notez les parenthèses autour de `0.1, target`).</span><span class="sxs-lookup"><span data-stu-id="179b7-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="179b7-291">En guise d’autre exemple, `CNOT(control, target)` peut être implémentée en tant que `Controlled X([control], target)`.</span><span class="sxs-lookup"><span data-stu-id="179b7-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="179b7-292">Si une cible doit être contrôlée par deux qubits de contrôle (CCNOT), nous pouvons utiliser `Controlled X([control1, control2], target)` instruction.</span><span class="sxs-lookup"><span data-stu-id="179b7-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="179b7-293">Exemples</span><span class="sxs-lookup"><span data-stu-id="179b7-293">Examples</span></span>

<span data-ttu-id="179b7-294">Cet exemple d’opération Q # provient de l’exemple [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) .</span><span class="sxs-lookup"><span data-stu-id="179b7-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="179b7-295">Dans les opérations, nous pouvons allouer qubits et utiliser des opérations de Quantum sur ces qubits, telles que `H` et `X`:</span><span class="sxs-lookup"><span data-stu-id="179b7-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
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

<span data-ttu-id="179b7-296">Cet exemple de fonction provient de l’exemple [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="179b7-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="179b7-297">Il contient du code purement classique.</span><span class="sxs-lookup"><span data-stu-id="179b7-297">It contains purely classical code.</span></span> <span data-ttu-id="179b7-298">Vous pouvez voir que, contrairement à l’exemple ci-dessus, aucun qubits n’est alloué et aucune opération de Quantum n’est utilisée.</span><span class="sxs-lookup"><span data-stu-id="179b7-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="179b7-299">Il est également possible qu’une fonction soit passée qubits pour traitement, comme dans cet exemple à partir de l’exemple [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) .</span><span class="sxs-lookup"><span data-stu-id="179b7-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="179b7-300">Les qubits sont passés à la fonction et utilisés pour le traitement, mais à aucun moment les États qubit eux-mêmes ne sont pas modifiés.</span><span class="sxs-lookup"><span data-stu-id="179b7-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

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
