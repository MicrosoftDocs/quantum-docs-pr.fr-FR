---
title: Utilisation de la Q# bibliothèque de valeurs numériques Microsoft
description: En savoir plus sur les types et les opérations disponibles dans la bibliothèque de valeurs numériques Quantum Microsoft.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: conceptual
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: 92efd3b8677d2f27bc59f986ce6c9e915cd23652
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856444"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="9fe40-103">Utilisation de la bibliothèque de valeurs numériques</span><span class="sxs-lookup"><span data-stu-id="9fe40-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="9fe40-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="9fe40-104">Overview</span></span>

<span data-ttu-id="9fe40-105">La bibliothèque de valeurs numériques est constituée de trois composants.</span><span class="sxs-lookup"><span data-stu-id="9fe40-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="9fe40-106">**Arithmétique d’entiers de base avec additions** d’entiers et comparateurs</span><span class="sxs-lookup"><span data-stu-id="9fe40-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="9fe40-107">**Fonctionnalités entières de haut niveau** qui s’appuient sur les fonctionnalités de base. Il comprend la multiplication, la Division, l’inversion, etc.  pour les entiers signés et non signés.</span><span class="sxs-lookup"><span data-stu-id="9fe40-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="9fe40-108">**Fonctionnalité arithmétique à virgule fixe** avec initialisation à virgule fixe, addition, multiplication, réciproque, évaluation polynomiale et mesure.</span><span class="sxs-lookup"><span data-stu-id="9fe40-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="9fe40-109">Vous pouvez accéder à tous ces composants à l’aide d’une seule `open` instruction :</span><span class="sxs-lookup"><span data-stu-id="9fe40-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="9fe40-110">Types</span><span class="sxs-lookup"><span data-stu-id="9fe40-110">Types</span></span>

<span data-ttu-id="9fe40-111">La bibliothèque de valeurs numériques prend en charge les types suivants :</span><span class="sxs-lookup"><span data-stu-id="9fe40-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="9fe40-112">**`LittleEndian`**: Tableau qubit `qArr : Qubit[]` qui représente un entier `qArr[0]` dénotant le bit le moins significatif.</span><span class="sxs-lookup"><span data-stu-id="9fe40-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="9fe40-113">**`SignedLittleEndian`**: Identique `LittleEndian` à, à ceci près qu’il représente un entier signé stocké dans le complément à deux.</span><span class="sxs-lookup"><span data-stu-id="9fe40-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="9fe40-114">**`FixedPoint`**: Représente un nombre réel constitué d’un tableau qubit `qArr2 : Qubit[]` et d’une position de point binaire `pos` , qui compte le nombre de chiffres binaires à gauche du point binaire.</span><span class="sxs-lookup"><span data-stu-id="9fe40-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="9fe40-115">`qArr2` est stocké de la même façon que `SignedLittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="9fe40-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="9fe40-116">Opérations</span><span class="sxs-lookup"><span data-stu-id="9fe40-116">Operations</span></span>

<span data-ttu-id="9fe40-117">Pour chacun des trois types ci-dessus, diverses opérations sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="9fe40-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="9fe40-118">Addition</span><span class="sxs-lookup"><span data-stu-id="9fe40-118">Addition</span></span>
    - <span data-ttu-id="9fe40-119">Comparaison</span><span class="sxs-lookup"><span data-stu-id="9fe40-119">Comparison</span></span>
    - <span data-ttu-id="9fe40-120">Multiplication</span><span class="sxs-lookup"><span data-stu-id="9fe40-120">Multiplication</span></span>
    - <span data-ttu-id="9fe40-121">Mise au carré</span><span class="sxs-lookup"><span data-stu-id="9fe40-121">Squaring</span></span>
    - <span data-ttu-id="9fe40-122">Division (avec reste)</span><span class="sxs-lookup"><span data-stu-id="9fe40-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="9fe40-123">Addition</span><span class="sxs-lookup"><span data-stu-id="9fe40-123">Addition</span></span>
    - <span data-ttu-id="9fe40-124">Comparaison</span><span class="sxs-lookup"><span data-stu-id="9fe40-124">Comparison</span></span>
    - <span data-ttu-id="9fe40-125">Complément modulo de la version 2</span><span class="sxs-lookup"><span data-stu-id="9fe40-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="9fe40-126">Multiplication</span><span class="sxs-lookup"><span data-stu-id="9fe40-126">Multiplication</span></span>
    - <span data-ttu-id="9fe40-127">Mise au carré</span><span class="sxs-lookup"><span data-stu-id="9fe40-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="9fe40-128">Préparation/initialisation à des valeurs classiques</span><span class="sxs-lookup"><span data-stu-id="9fe40-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="9fe40-129">Addition (constante classique ou autre point fixe quantique)</span><span class="sxs-lookup"><span data-stu-id="9fe40-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="9fe40-130">Comparaison</span><span class="sxs-lookup"><span data-stu-id="9fe40-130">Comparison</span></span>
    - <span data-ttu-id="9fe40-131">Multiplication</span><span class="sxs-lookup"><span data-stu-id="9fe40-131">Multiplication</span></span>
    - <span data-ttu-id="9fe40-132">Mise au carré</span><span class="sxs-lookup"><span data-stu-id="9fe40-132">Squaring</span></span>
    - <span data-ttu-id="9fe40-133">Évaluation polynomiale avec spécialisation pour les fonctions paires et impaires</span><span class="sxs-lookup"><span data-stu-id="9fe40-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="9fe40-134">Réciproque (1/x)</span><span class="sxs-lookup"><span data-stu-id="9fe40-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="9fe40-135">Mesure (double classique)</span><span class="sxs-lookup"><span data-stu-id="9fe40-135">Measurement (classical Double)</span></span>

<span data-ttu-id="9fe40-136">Pour plus d’informations et une documentation détaillée sur chacune de ces opérations, consultez les Q# documents de référence sur les bibliothèques sur [docs.Microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="9fe40-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="9fe40-137">Exemple : ajout d’un entier</span><span class="sxs-lookup"><span data-stu-id="9fe40-137">Sample: Integer addition</span></span>

<span data-ttu-id="9fe40-138">À titre d’exemple, considérez l’opération $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ autrement dit, une opération qui accepte un entier n-qubit $x $ et un n-ou (n + 1)-qubit inscrire $y $ comme entrée, le dernier mappé à la somme $ (x + y) $.</span><span class="sxs-lookup"><span data-stu-id="9fe40-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="9fe40-139">Notez que la somme est calculée modulo $2 ^ n $ si $y $ est stocké dans un registre $n $ bits.</span><span class="sxs-lookup"><span data-stu-id="9fe40-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="9fe40-140">À l’aide du kit de développement quantique, cette opération peut être appliquée comme suit :</span><span class="sxs-lookup"><span data-stu-id="9fe40-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="9fe40-141">Exemple : évaluation des fonctions Smooth</span><span class="sxs-lookup"><span data-stu-id="9fe40-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="9fe40-142">Pour évaluer des fonctions lissées telles que $ \sin (x) $ sur un ordinateur Quantum, où $x $ est un `FixedPoint` numéro Quantum, la bibliothèque de valeurs de kit de développement quantum fournit les opérations `EvaluatePolynomialFxP` et `Evaluate[Even/Odd]PolynomialFxP` .</span><span class="sxs-lookup"><span data-stu-id="9fe40-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="9fe40-143">La première, `EvaluatePolynomialFxP` , permet d’évaluer un polynomial au format $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $ où $d $ indique le *degré*.</span><span class="sxs-lookup"><span data-stu-id="9fe40-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="9fe40-144">Pour ce faire, tout ce qui est nécessaire est le coefficient polynomial `[a_0,..., a_d]` (de type `Double[]` ), l’entrée `x : FixedPoint` et la sortie `y : FixedPoint` (initialement zéro) :</span><span class="sxs-lookup"><span data-stu-id="9fe40-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="9fe40-145">Le résultat, $P (x) = 1 + 2x $, est stocké dans `yFxP` .</span><span class="sxs-lookup"><span data-stu-id="9fe40-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="9fe40-146">Le deuxième, `EvaluateEvenPolynomialFxP` , et le troisième, `EvaluateOddPolynomialFxP` sont des spécialisations pour les cas de fonctions paires et impaires, respectivement.</span><span class="sxs-lookup"><span data-stu-id="9fe40-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="9fe40-147">Autrement dit, pour une fonction pair/impair $f (x) $ et $ $ P_ {même} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ est bien approximatif en $P _ {même} (x) $ ou $P _ {impaire} (x) : = x\cdot P_ {pair} (x) $, respectivement.</span><span class="sxs-lookup"><span data-stu-id="9fe40-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="9fe40-148">Dans Q# , ces deux cas peuvent être gérés comme suit :</span><span class="sxs-lookup"><span data-stu-id="9fe40-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="9fe40-149">qui évalue $P _ {même} (x) = 1 + 2x ^ 2 $, et</span><span class="sxs-lookup"><span data-stu-id="9fe40-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="9fe40-150">qui évalue $P _ {impair} (x) = x + 2x ^ 3 $.</span><span class="sxs-lookup"><span data-stu-id="9fe40-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="9fe40-151">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="9fe40-151">More samples</span></span>

<span data-ttu-id="9fe40-152">Vous trouverez d’autres exemples dans le [référentiel d’exemples principal](https://github.com/Microsoft/Quantum).</span><span class="sxs-lookup"><span data-stu-id="9fe40-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="9fe40-153">Pour commencer, clonez le référentiel et ouvrez le `Numerics` sous-dossier :</span><span class="sxs-lookup"><span data-stu-id="9fe40-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics
```

<span data-ttu-id="9fe40-154">Puis, `cd` dans l’un des exemples de dossiers et exécutez l’exemple via</span><span class="sxs-lookup"><span data-stu-id="9fe40-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
