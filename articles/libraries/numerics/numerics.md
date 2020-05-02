---
title: 'Utilisation de la bibliothèque numérique Microsoft Q #'
description: En savoir plus sur les types et les opérations disponibles dans la bibliothèque de valeurs numériques Quantum Microsoft.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82677106"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="8c889-103">Utilisation de la bibliothèque de valeurs numériques</span><span class="sxs-lookup"><span data-stu-id="8c889-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="8c889-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="8c889-104">Overview</span></span>

<span data-ttu-id="8c889-105">La bibliothèque de valeurs numériques est constituée de trois composants.</span><span class="sxs-lookup"><span data-stu-id="8c889-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="8c889-106">**Arithmétique d’entiers de base avec additions** d’entiers et comparateurs</span><span class="sxs-lookup"><span data-stu-id="8c889-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="8c889-107">**Fonctionnalités entières de haut niveau** qui s’appuient sur les fonctionnalités de base. Il comprend la multiplication, la Division, l’inversion, etc.  pour les entiers signés et non signés.</span><span class="sxs-lookup"><span data-stu-id="8c889-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="8c889-108">**Fonctionnalité arithmétique à virgule fixe** avec initialisation à virgule fixe, addition, multiplication, réciproque, évaluation polynomiale et mesure.</span><span class="sxs-lookup"><span data-stu-id="8c889-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="8c889-109">Vous pouvez accéder à tous ces composants à l’aide `open` d’une seule instruction :</span><span class="sxs-lookup"><span data-stu-id="8c889-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="8c889-110">Types</span><span class="sxs-lookup"><span data-stu-id="8c889-110">Types</span></span>

<span data-ttu-id="8c889-111">La bibliothèque de valeurs numériques prend en charge les types suivants :</span><span class="sxs-lookup"><span data-stu-id="8c889-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="8c889-112">**`LittleEndian`**: Tableau `qArr : Qubit[]` qubit qui représente un entier `qArr[0]` dénotant le bit le moins significatif.</span><span class="sxs-lookup"><span data-stu-id="8c889-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="8c889-113">**`SignedLittleEndian`**: Identique `LittleEndian` à, à ceci près qu’il représente un entier signé stocké dans le complément à deux.</span><span class="sxs-lookup"><span data-stu-id="8c889-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="8c889-114">**`FixedPoint`**: Représente un nombre réel constitué d’un tableau `qArr2 : Qubit[]` qubit et d’une position `pos`de point binaire, qui compte le nombre de chiffres binaires à gauche du point binaire.</span><span class="sxs-lookup"><span data-stu-id="8c889-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="8c889-115">`qArr2`est stocké de la même façon `SignedLittleEndian`que.</span><span class="sxs-lookup"><span data-stu-id="8c889-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="8c889-116">Opérations</span><span class="sxs-lookup"><span data-stu-id="8c889-116">Operations</span></span>

<span data-ttu-id="8c889-117">Pour chacun des trois types ci-dessus, diverses opérations sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="8c889-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="8c889-118">Addition</span><span class="sxs-lookup"><span data-stu-id="8c889-118">Addition</span></span>
    - <span data-ttu-id="8c889-119">Comparaison</span><span class="sxs-lookup"><span data-stu-id="8c889-119">Comparison</span></span>
    - <span data-ttu-id="8c889-120">Multiplication</span><span class="sxs-lookup"><span data-stu-id="8c889-120">Multiplication</span></span>
    - <span data-ttu-id="8c889-121">Mise au carré</span><span class="sxs-lookup"><span data-stu-id="8c889-121">Squaring</span></span>
    - <span data-ttu-id="8c889-122">Division (avec reste)</span><span class="sxs-lookup"><span data-stu-id="8c889-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="8c889-123">Addition</span><span class="sxs-lookup"><span data-stu-id="8c889-123">Addition</span></span>
    - <span data-ttu-id="8c889-124">Comparaison</span><span class="sxs-lookup"><span data-stu-id="8c889-124">Comparison</span></span>
    - <span data-ttu-id="8c889-125">Complément modulo de la version 2</span><span class="sxs-lookup"><span data-stu-id="8c889-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="8c889-126">Multiplication</span><span class="sxs-lookup"><span data-stu-id="8c889-126">Multiplication</span></span>
    - <span data-ttu-id="8c889-127">Mise au carré</span><span class="sxs-lookup"><span data-stu-id="8c889-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="8c889-128">Préparation/initialisation à des valeurs classiques</span><span class="sxs-lookup"><span data-stu-id="8c889-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="8c889-129">Addition (constante classique ou autre point fixe quantique)</span><span class="sxs-lookup"><span data-stu-id="8c889-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="8c889-130">Comparaison</span><span class="sxs-lookup"><span data-stu-id="8c889-130">Comparison</span></span>
    - <span data-ttu-id="8c889-131">Multiplication</span><span class="sxs-lookup"><span data-stu-id="8c889-131">Multiplication</span></span>
    - <span data-ttu-id="8c889-132">Mise au carré</span><span class="sxs-lookup"><span data-stu-id="8c889-132">Squaring</span></span>
    - <span data-ttu-id="8c889-133">Évaluation polynomiale avec spécialisation pour les fonctions paires et impaires</span><span class="sxs-lookup"><span data-stu-id="8c889-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="8c889-134">Réciproque (1/x)</span><span class="sxs-lookup"><span data-stu-id="8c889-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="8c889-135">Mesure (double classique)</span><span class="sxs-lookup"><span data-stu-id="8c889-135">Measurement (classical Double)</span></span>

<span data-ttu-id="8c889-136">Pour plus d’informations et pour obtenir une documentation détaillée sur chacune de ces opérations, consultez les documents de référence sur la bibliothèque Q # sur [docs.Microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="8c889-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="8c889-137">Exemple : ajout d’un entier</span><span class="sxs-lookup"><span data-stu-id="8c889-137">Sample: Integer addition</span></span>

<span data-ttu-id="8c889-138">À titre d’exemple, considérez l’opération $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ autrement dit, une opération qui accepte un entier n-qubit $x $ et un n-ou (n + 1)-qubit inscrire $y $ comme entrée, le dernier mappé à la somme $ (x + y) $.</span><span class="sxs-lookup"><span data-stu-id="8c889-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="8c889-139">Notez que la somme est calculée modulo $2 ^ n $ si $y $ est stocké dans un registre $n $ bits.</span><span class="sxs-lookup"><span data-stu-id="8c889-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="8c889-140">À l’aide du kit de développement quantique, cette opération peut être appliquée comme suit :</span><span class="sxs-lookup"><span data-stu-id="8c889-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
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

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="8c889-141">Exemple : évaluation des fonctions Smooth</span><span class="sxs-lookup"><span data-stu-id="8c889-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="8c889-142">Pour évaluer des fonctions lissées telles que $ \sin (x) $ sur un ordinateur Quantum, où $x $ est `FixedPoint` un numéro Quantum, la bibliothèque de valeurs de kit de développement `EvaluatePolynomialFxP` Quantum `Evaluate[Even/Odd]PolynomialFxP`fournit les opérations et.</span><span class="sxs-lookup"><span data-stu-id="8c889-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="8c889-143">La première, `EvaluatePolynomialFxP`, permet d’évaluer un polynomial au format $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $ où $d $ indique le *degré*.</span><span class="sxs-lookup"><span data-stu-id="8c889-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="8c889-144">Pour ce faire, tout ce qui est nécessaire est le coefficient polynomial `[a_0,..., a_d]` (de type `Double[]`), l’entrée `x : FixedPoint` et la sortie `y : FixedPoint` (initialement zéro) :</span><span class="sxs-lookup"><span data-stu-id="8c889-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="8c889-145">Le résultat, $P (x) = 1 + 2x $, est stocké dans `yFxP`.</span><span class="sxs-lookup"><span data-stu-id="8c889-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="8c889-146">Le deuxième, `EvaluateEvenPolynomialFxP`, et le troisième `EvaluateOddPolynomialFxP`, sont des spécialisations pour les cas de fonctions paires et impaires, respectivement.</span><span class="sxs-lookup"><span data-stu-id="8c889-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="8c889-147">Autrement dit, pour une fonction pair/impair $f (x) $ et $ $ P_ {même} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ est bien approximatif en $P _ {même} (x) $ ou $P _ {impaire} (x) : = x\cdot P_ {pair} (x) $, respectivement.</span><span class="sxs-lookup"><span data-stu-id="8c889-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="8c889-148">Dans Q #, ces deux cas peuvent être gérés comme suit :</span><span class="sxs-lookup"><span data-stu-id="8c889-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="8c889-149">qui évalue $P _ {même} (x) = 1 + 2x ^ 2 $, et</span><span class="sxs-lookup"><span data-stu-id="8c889-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="8c889-150">qui évalue $P _ {impair} (x) = x + 2x ^ 3 $.</span><span class="sxs-lookup"><span data-stu-id="8c889-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="8c889-151">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="8c889-151">More samples</span></span>

<span data-ttu-id="8c889-152">Vous trouverez d’autres exemples dans le [référentiel d’exemples principal](https://github.com/Microsoft/Quantum).</span><span class="sxs-lookup"><span data-stu-id="8c889-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="8c889-153">Pour commencer, clonez le référentiel et ouvrez le `Numerics` sous-dossier :</span><span class="sxs-lookup"><span data-stu-id="8c889-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="8c889-154">Puis, `cd` dans l’un des exemples de dossiers et exécutez l’exemple via</span><span class="sxs-lookup"><span data-stu-id="8c889-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
