---
title: Contrôles de Flow dans le Q# libararies standard
description: En savoir plus sur les opérations et les fonctions de contrôle de Flow dans la Q# bibliothèque standard Microsoft.
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1cfef50cf2bbecd2043972a662edd8120c5570ec
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835619"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="4df46-103">Contrôle de l’ordre supérieur</span><span class="sxs-lookup"><span data-stu-id="4df46-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="4df46-104">L’un des principaux rôles de la bibliothèque standard est de faciliter l’expression d’idées algorithmiques de haut niveau en tant que [programmes quantiques](https://en.wikipedia.org/wiki/Quantum_programming).</span><span class="sxs-lookup"><span data-stu-id="4df46-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="4df46-105">Par conséquent, Q# Canon fournit une variété de constructions de contrôle de Flow, chacune implémentée à l’aide d’une application partielle de fonctions et d’opérations.</span><span class="sxs-lookup"><span data-stu-id="4df46-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="4df46-106">Si vous sautez immédiatement dans un exemple, considérez le cas dans lequel vous souhaitez construire une « échelle CNOTIN » sur un registre :</span><span class="sxs-lookup"><span data-stu-id="4df46-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="4df46-107">Nous pouvons exprimer ce modèle à l’aide d’itérations et de `for` boucles :</span><span class="sxs-lookup"><span data-stu-id="4df46-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="4df46-108">Exprimée en termes de <xref:microsoft.quantum.canon.applytoeachca> et de fonctions de manipulation de tableau telles que <xref:microsoft.quantum.arrays.zip> , toutefois, cette opération est beaucoup plus rapide et plus facile à lire :</span><span class="sxs-lookup"><span data-stu-id="4df46-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="4df46-109">Dans le reste de cette section, nous vous fournirons un certain nombre d’exemples d’utilisation des diverses opérations et fonctions de contrôle de workflow fournies par Canon pour exprimer les programmes Quantum de manière compacte.</span><span class="sxs-lookup"><span data-stu-id="4df46-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="4df46-110">Application d’opérations et de fonctions sur des tableaux et des plages</span><span class="sxs-lookup"><span data-stu-id="4df46-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="4df46-111">L’une des abstractions principales fournies par Canon est celle de l’itération.</span><span class="sxs-lookup"><span data-stu-id="4df46-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="4df46-112">Par exemple, considérez une unité de la forme $U \otimes U \otimes \cdots \otimes U $ pour une $U unitaire $.</span><span class="sxs-lookup"><span data-stu-id="4df46-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="4df46-113">Dans Q# , nous pouvons utiliser <xref:microsoft.quantum.arrays.indexrange> pour représenter cela comme une `for` boucle sur un registre :</span><span class="sxs-lookup"><span data-stu-id="4df46-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="4df46-114">Nous pouvons ensuite utiliser cette nouvelle opération `HAll(register)` pour appliquer $H \Otimes h \otimes \cdots \Otimes h $.</span><span class="sxs-lookup"><span data-stu-id="4df46-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="4df46-115">Cette opération est lourde, cependant, en particulier dans un algorithme plus grand.</span><span class="sxs-lookup"><span data-stu-id="4df46-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="4df46-116">En outre, cette approche est spécialisée pour l’opération particulière que nous souhaitons appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="4df46-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="4df46-117">Nous pouvons utiliser le fait que les opérations sont de première classe pour exprimer ce concept algorithmique plus explicitement :</span><span class="sxs-lookup"><span data-stu-id="4df46-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="4df46-118">Ici, le suffixe `CA` indique que l’appel à `ApplyToEach` est lui-même adjointable et contrôlable.</span><span class="sxs-lookup"><span data-stu-id="4df46-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="4df46-119">Ainsi, si `U` prend en charge `Adjoint` et `Controlled` , les lignes suivantes sont équivalentes :</span><span class="sxs-lookup"><span data-stu-id="4df46-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="4df46-120">En particulier, cela signifie que les appels à `ApplyToEachCA` peuvent apparaître dans les opérations pour lesquelles une spécialisation voisine est générée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="4df46-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="4df46-121">De même, <xref:microsoft.quantum.canon.applytoeachindex> est utile pour représenter les modèles du formulaire `U(0, targets[0]); U(1, targets[1]); ...` et offre des versions pour chaque combinaison d’functors prise en charge par son entrée.</span><span class="sxs-lookup"><span data-stu-id="4df46-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="4df46-122">`ApplyToEach` est paramétrable de type de sorte qu’il puisse être utilisé avec des opérations qui prennent des entrées autres que `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="4df46-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="4df46-123">Par exemple, supposons qu' `codeBlocks` il s’agit d’un tableau de <xref:microsoft.quantum.errorcorrection.logicalregister> valeurs qui doivent être récupérées.</span><span class="sxs-lookup"><span data-stu-id="4df46-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="4df46-124">Ensuite, `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` applique le code de correction des erreurs `code` et la fonction `recoveryFn` de récupération à chaque bloc indépendamment.</span><span class="sxs-lookup"><span data-stu-id="4df46-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="4df46-125">Cela est également valable pour les entrées classiques : `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` applique une rotation de $ \pi/$2 sur $X $ suivie d’une rotation de $pi/$3 sur $Y $.</span><span class="sxs-lookup"><span data-stu-id="4df46-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="4df46-126">Q#Canon prend également en charge les modèles d’énumération classiques familiers à la programmation fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="4df46-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="4df46-127">Par exemple, <xref:microsoft.quantum.arrays.fold> implémente le modèle $f (f (f (s \_ {\text{initial}}, x \_ 0), x \_ 1), \dots) $ pour réduire une fonction sur une liste.</span><span class="sxs-lookup"><span data-stu-id="4df46-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="4df46-128">Ce modèle peut être utilisé pour implémenter des sommes, des produits, des minima, des maxima et d’autres fonctions de ce type :</span><span class="sxs-lookup"><span data-stu-id="4df46-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="4df46-129">De même, les fonctions comme <xref:microsoft.quantum.arrays.mapped> et <xref:microsoft.quantum.arrays.mappedbyindex> peuvent être utilisées pour exprimer les concepts de programmation fonctionnelle dans Q# .</span><span class="sxs-lookup"><span data-stu-id="4df46-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="4df46-130">Composer des opérations et des fonctions</span><span class="sxs-lookup"><span data-stu-id="4df46-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="4df46-131">Les constructions de workflow de contrôle offertes par Canon prennent les opérations et fonctionnent comme entrées, de sorte qu’il est utile de pouvoir composer plusieurs opérations ou fonctions en un seul appelable.</span><span class="sxs-lookup"><span data-stu-id="4df46-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="4df46-132">Par exemple, le modèle $UVU ^ {\dagger} $ est extrêmement courant dans la programmation quantique, de sorte que Canon fournit l’opération <xref:microsoft.quantum.canon.applywith> en tant qu’abstraction pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="4df46-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="4df46-133">Cette abstraction permet également une meilleure conformité dans les circuits, car il `Controlled` `U(qubit); V(qubit); Adjoint U(qubit);` n’est pas nécessaire d’agir sur chaque séquence `U` .</span><span class="sxs-lookup"><span data-stu-id="4df46-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="4df46-134">Pour le voir, $c (U) $ est l’unité représentant `Controlled U([control], target)` et laisser $c (V) $ être défini de la même façon.</span><span class="sxs-lookup"><span data-stu-id="4df46-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="4df46-135">Ensuite, pour un état arbitraire $ \ket{\Psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (UVU ^ {\dagger} \ket{\psi}) \\ \\ & = (\boldone \otimes u) (c (V)) (\boldone \otimes U ^ \dagger) \ket {1} \otimes \ket{\Psi}.</span><span class="sxs-lookup"><span data-stu-id="4df46-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="4df46-136">\end{align} par la définition de `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="4df46-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="4df46-137">En revanche, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\Psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\Psi}) \\ \\ & = (\Boldone \otimes u) (c (V)) (\boldone \otimes U ^ \dagger) \ket {0} \otimes \ket{\Psi}.</span><span class="sxs-lookup"><span data-stu-id="4df46-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="4df46-138">\end{align} par linéarité, nous pouvons conclure que nous pouvons factoriser $U $ Out de cette manière pour tous les États d’entrée.</span><span class="sxs-lookup"><span data-stu-id="4df46-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="4df46-139">Autrement dit, $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="4df46-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="4df46-140">Étant donné que les opérations de contrôle peuvent être coûteuses en général, l’utilisation de variantes contrôlées telles que `WithC` et `WithCA` peut aider à réduire le nombre d’functors de contrôle qui doivent être appliqués.</span><span class="sxs-lookup"><span data-stu-id="4df46-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="4df46-141">Une autre conséquence de la factorisation $U $ est que nous n’avons même pas besoin de savoir comment appliquer le `Controlled` functor à `U` .</span><span class="sxs-lookup"><span data-stu-id="4df46-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="4df46-142">`ApplyWithCA` par conséquent, la signature est plus faible que celle qui est attendue :</span><span class="sxs-lookup"><span data-stu-id="4df46-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="4df46-143">De même, <xref:microsoft.quantum.canon.bound> produit des opérations qui appliquent une séquence d’autres opérations à leur tour.</span><span class="sxs-lookup"><span data-stu-id="4df46-143">Similarly, <xref:microsoft.quantum.canon.bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="4df46-144">Par exemple, les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="4df46-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="4df46-145">La combinaison avec les modèles d’itération peut s’avérer particulièrement utile :</span><span class="sxs-lookup"><span data-stu-id="4df46-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="4df46-146">Composition chronologique</span><span class="sxs-lookup"><span data-stu-id="4df46-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="4df46-147">Nous pouvons continuer en pensant au contrôle de Flow en termes d’application partielle et de fonctions classiques, et peuvent modéliser des concepts de Quantum encore plus sophistiqués en termes de contrôle de la fluidité classique.</span><span class="sxs-lookup"><span data-stu-id="4df46-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="4df46-148">Cette analogie est faite de manière précise par la reconnaissance selon laquelle les opérateurs d’unités correspondent exactement aux effets secondaires des opérations d’appel, de telle sorte que toute décomposition d’opérateurs unitaires en termes d’autres opérateurs unitaires corresponde à la construction d’une séquence d’appel particulière pour les sous-routines classiques qui émettent des instructions pour agir en tant qu’opérateurs unitaires particuliers.</span><span class="sxs-lookup"><span data-stu-id="4df46-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="4df46-149">Dans cette vue, `Bound` est précisément la représentation du produit de la matrice, car `Bound([A, B])(target)` est équivalent à `A(target); B(target);` , qui, à son tour, correspond à la séquence d’appel correspondant à $BA $.</span><span class="sxs-lookup"><span data-stu-id="4df46-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="4df46-150">Un exemple plus sophistiqué est l' [expansion Trotter – Suzuki](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="4df46-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="4df46-151">Comme indiqué dans la section relative à la représentation du générateur dynamique des [structures de données](xref:microsoft.quantum.libraries.data-structures), l’expansion Trotter – Suzuki offre un moyen particulièrement utile d’exprimer des exponentiels de matrice.</span><span class="sxs-lookup"><span data-stu-id="4df46-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="4df46-152">Par exemple, l’application de l’expansion à son ordre le plus bas donne à tous les opérateurs $A $ et $B $ de sorte que $A = A ^ \dagger $ et $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ : Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (i A t/n) \exp (i B t/n) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="4df46-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="4df46-153">\end{align} en commun, cela signifie que nous pouvons approximativement faire évoluer un État sous $A + B $ en évoluant alternativement sous $A $ et $B $ seul.</span><span class="sxs-lookup"><span data-stu-id="4df46-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="4df46-154">Si nous représentons l’évolution sous $A $ par une opération `A : (Double, Qubit[]) => Unit` qui applique $e ^ {t A} $, la représentation de l’expansion Trotter – Suzuki en termes de réorganisation des séquences appelées devient évidente.</span><span class="sxs-lookup"><span data-stu-id="4df46-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="4df46-155">Concrètement, étant donné une opération `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` telle que `A = U(0, _, _)` et `B = U(1, _, _)` , nous pouvons définir une nouvelle opération représentant l’intégrale de `U` au moment $t $ en générant des séquences de la forme</span><span class="sxs-lookup"><span data-stu-id="4df46-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="4df46-156">À ce stade, nous pouvons maintenant expliquer l’expansion Trotter – Suzuki *sans référence à la mécanique des quantums*.</span><span class="sxs-lookup"><span data-stu-id="4df46-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="4df46-157">L’expansion est effectivement un modèle d’itération très particulier motivé par $ \eqref{EQ : Trotter-Suzuki-0} $.</span><span class="sxs-lookup"><span data-stu-id="4df46-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="4df46-158">Ce modèle d’itération est implémenté par <xref:microsoft.quantum.canon.decomposeintotimestepsca> :</span><span class="sxs-lookup"><span data-stu-id="4df46-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="4df46-159">La signature de `DecomposeIntoTimeStepsCA` suit un modèle commun dans Q# , où les collections qui peuvent être sauvegardées par des tableaux ou par un élément qui calcule des éléments à la volée sont représentées par des tuples dont les premiers éléments sont des `Int` valeurs indiquant leurs longueurs.</span><span class="sxs-lookup"><span data-stu-id="4df46-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="4df46-160">Ensemble : contrôle des opérations</span><span class="sxs-lookup"><span data-stu-id="4df46-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="4df46-161">Enfin, Canon s’appuie sur `Controlled` functor en fournissant des méthodes supplémentaires pour la condition des opérations quantiques.</span><span class="sxs-lookup"><span data-stu-id="4df46-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="4df46-162">Il est courant, surtout dans le cas de l’arithmétique quantique, de conditionner les opérations sur les États de base de calcul autres que $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="4df46-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="4df46-163">À l’aide des opérations de contrôle et des fonctions présentées ci-dessus, nous pouvons obtenir des conditions de Quantum plus générales dans une instruction unique.</span><span class="sxs-lookup"><span data-stu-id="4df46-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="4df46-164">Passons à la procédure <xref:microsoft.quantum.canon.controlledonbitstring> (paramètres de type sans réseau), puis nous décomposons les éléments un par un.</span><span class="sxs-lookup"><span data-stu-id="4df46-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="4df46-165">La première chose à faire est de définir une opération qui fait réellement le gros du levage de l’implémentation du contrôle sur des États de base de calcul arbitraires.</span><span class="sxs-lookup"><span data-stu-id="4df46-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="4df46-166">Nous n’appellerons pas cette opération directement, mais nous ajoutons donc `_` au début du nom pour indiquer qu’il s’agit d’une implémentation d’une autre construction ailleurs.</span><span class="sxs-lookup"><span data-stu-id="4df46-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="4df46-167">Notez que nous prenons une chaîne de bits, représentée sous la forme d’un `Bool` tableau, que nous utilisons pour spécifier le conditionnement que nous souhaitons appliquer à l’opération `oracle` que nous avons donnée.</span><span class="sxs-lookup"><span data-stu-id="4df46-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="4df46-168">Étant donné que cette opération fait directement l’application, nous devons également prendre les registres de contrôle et cibles, représentés ici sous la forme `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="4df46-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="4df46-169">Ensuite, nous constatons que le contrôle de l’état de la base de calcul $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots s \_ {n-1}} $ pour une chaîne de bits $ \vec{s} $ peut être réalisé en transformant $ \ket{\vec{s}} $ en $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="4df46-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="4df46-170">En particulier, $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="4df46-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="4df46-171">Depuis $X ^ {\dagger} = X $, cela implique que $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{\vec{s}} $.</span><span class="sxs-lookup"><span data-stu-id="4df46-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="4df46-172">Par conséquent, nous pouvons appliquer $P = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} $, appliquer `Controlled oracle` et transformer en $ \vec{s} $.</span><span class="sxs-lookup"><span data-stu-id="4df46-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="4df46-173">Cette construction est précise `ApplyWith` , donc nous écrivons le corps de notre nouvelle opération en conséquence :</span><span class="sxs-lookup"><span data-stu-id="4df46-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="4df46-174">Ici, nous avons utilisé <xref:microsoft.quantum.canon.applypaulifrombitstring> pour appliquer $P $, partiellement appliqué sur sa cible pour une utilisation avec `ApplyWith` .</span><span class="sxs-lookup"><span data-stu-id="4df46-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="4df46-175">Notez, toutefois, que nous devons transformer le registre de *contrôle* au format souhaité, donc nous appliquons partiellement l’opération interne `(Controlled oracle)` sur la *cible*.</span><span class="sxs-lookup"><span data-stu-id="4df46-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="4df46-176">Cela permet de mettre en place `ApplyWith` le registre de contrôle avec $P $, exactement comme nous le souhaitons.</span><span class="sxs-lookup"><span data-stu-id="4df46-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="4df46-177">À ce stade, nous avons pu le faire, mais cela ne suffit pas à ce que notre nouvelle opération ne semble pas être l’application de `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="4df46-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="4df46-178">Par conséquent, nous avons fini de définir notre nouveau concept de workflow en écrivant une fonction qui prend le contrôle Oracle et qui retourne une nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="4df46-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="4df46-179">De cette façon, notre nouvelle fonction ressemble beaucoup `Controlled` à, illustrant que nous pouvons facilement définir de nouvelles constructions de contrôle de contrôle puissantes à l’aide Q# de et de Canon :</span><span class="sxs-lookup"><span data-stu-id="4df46-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
