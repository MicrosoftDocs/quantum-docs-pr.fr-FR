---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855530"
---
# <a name="decomposedon-function"></a><span data-ttu-id="178a1-102">DecomposedOn fonction)</span><span class="sxs-lookup"><span data-stu-id="178a1-102">DecomposedOn function</span></span>

<span data-ttu-id="178a1-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="178a1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="178a1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="178a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="178a1-105">Décompose une permutation sur une variable</span><span class="sxs-lookup"><span data-stu-id="178a1-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="178a1-106">Description</span><span class="sxs-lookup"><span data-stu-id="178a1-106">Description</span></span>

<span data-ttu-id="178a1-107">Étant donné une permutation $ \pi $ ( `perm` ) et un index $i $ ( `index` ), cette méthode retourne trois permutations $ ((\ pi_l, \ Pi_R), \pi') $, de telle sorte que les images de $ \ pi_l $ et $ \ Pi_R $ ne changent pas les bits dans leurs éléments aux index autres que $i $ et les images de $ \pi' $ ne changent pas le bit $i $ dans leurs éléments.</span><span class="sxs-lookup"><span data-stu-id="178a1-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="178a1-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="178a1-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="178a1-109">Perm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="178a1-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="178a1-110">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="178a1-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="178a1-111">Sortie : (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="178a1-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="178a1-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="178a1-112">Example</span></span>

<span data-ttu-id="178a1-113">Supposons que l’entrée est Perm = [0, 2, 3, 5, 7, 1, 4, 6] et index = 0, alors cette fonction calcule trois permutations basées sur le tableau suivant, qui répertorie la permutation `perm` en notation binaire avec les éléments dans le groupe A et les images dans le groupe D.  Les colonnes répertorient les index binaires.</span><span class="sxs-lookup"><span data-stu-id="178a1-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="178a1-114">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="178a1-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="178a1-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-115">2 1 0</span></span> | <span data-ttu-id="178a1-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-116">2 1 0</span></span> | <span data-ttu-id="178a1-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-117">2 1 0</span></span> | <span data-ttu-id="178a1-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="178a1-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-119">0 0 0</span></span> |       |       | <span data-ttu-id="178a1-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-120">0 0 0</span></span> | <span data-ttu-id="178a1-121">0</span><span class="sxs-lookup"><span data-stu-id="178a1-121">0</span></span>
| <span data-ttu-id="178a1-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-122">0 0 1</span></span> |       |       | <span data-ttu-id="178a1-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-123">0 1 0</span></span> | <span data-ttu-id="178a1-124">2</span><span class="sxs-lookup"><span data-stu-id="178a1-124">2</span></span>
| <span data-ttu-id="178a1-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-125">0 1 0</span></span> |       |       | <span data-ttu-id="178a1-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-126">0 1 1</span></span> | <span data-ttu-id="178a1-127">3</span><span class="sxs-lookup"><span data-stu-id="178a1-127">3</span></span>
| <span data-ttu-id="178a1-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-128">0 1 1</span></span> |       |       | <span data-ttu-id="178a1-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-129">1 0 1</span></span> | <span data-ttu-id="178a1-130">5</span><span class="sxs-lookup"><span data-stu-id="178a1-130">5</span></span>
| <span data-ttu-id="178a1-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-131">1 0 0</span></span> |       |       | <span data-ttu-id="178a1-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-132">1 1 1</span></span> | <span data-ttu-id="178a1-133">7</span><span class="sxs-lookup"><span data-stu-id="178a1-133">7</span></span>
| <span data-ttu-id="178a1-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-134">1 0 1</span></span> |       |       | <span data-ttu-id="178a1-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-135">0 0 1</span></span> | <span data-ttu-id="178a1-136">1</span><span class="sxs-lookup"><span data-stu-id="178a1-136">1</span></span>
| <span data-ttu-id="178a1-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-137">1 1 0</span></span> |       |       | <span data-ttu-id="178a1-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-138">1 0 0</span></span> | <span data-ttu-id="178a1-139">4</span><span class="sxs-lookup"><span data-stu-id="178a1-139">4</span></span>
| <span data-ttu-id="178a1-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-140">1 1 1</span></span> |       |       | <span data-ttu-id="178a1-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-141">1 1 0</span></span> | <span data-ttu-id="178a1-142">6</span><span class="sxs-lookup"><span data-stu-id="178a1-142">6</span></span>

<span data-ttu-id="178a1-143">Toutes les valeurs des index qui ne sont pas égales à 0 (= index) sont copiées de A à B et de D à C.</span><span class="sxs-lookup"><span data-stu-id="178a1-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="178a1-144">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="178a1-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="178a1-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-145">2 1 0</span></span> | <span data-ttu-id="178a1-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-146">2 1 0</span></span> | <span data-ttu-id="178a1-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-147">2 1 0</span></span> | <span data-ttu-id="178a1-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="178a1-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-149">0 0 0</span></span> | <span data-ttu-id="178a1-150">0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-150">0 0</span></span>   | <span data-ttu-id="178a1-151">0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-151">0 0</span></span>   | <span data-ttu-id="178a1-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-152">0 0 0</span></span> |
| <span data-ttu-id="178a1-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-153">0 0 1</span></span> | <span data-ttu-id="178a1-154">0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-154">0 0</span></span>   | <span data-ttu-id="178a1-155">0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-155">0 1</span></span>   | <span data-ttu-id="178a1-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-156">0 1 0</span></span> |
| <span data-ttu-id="178a1-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-157">0 1 0</span></span> | <span data-ttu-id="178a1-158">0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-158">0 1</span></span>   | <span data-ttu-id="178a1-159">0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-159">0 1</span></span>   | <span data-ttu-id="178a1-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-160">0 1 1</span></span> |
| <span data-ttu-id="178a1-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-161">0 1 1</span></span> | <span data-ttu-id="178a1-162">0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-162">0 1</span></span>   | <span data-ttu-id="178a1-163">1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-163">1 0</span></span>   | <span data-ttu-id="178a1-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-164">1 0 1</span></span> |
| <span data-ttu-id="178a1-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-165">1 0 0</span></span> | <span data-ttu-id="178a1-166">1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-166">1 0</span></span>   | <span data-ttu-id="178a1-167">1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-167">1 1</span></span>   | <span data-ttu-id="178a1-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-168">1 1 1</span></span> |
| <span data-ttu-id="178a1-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-169">1 0 1</span></span> | <span data-ttu-id="178a1-170">1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-170">1 0</span></span>   | <span data-ttu-id="178a1-171">0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-171">0 0</span></span>   | <span data-ttu-id="178a1-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-172">0 0 1</span></span> |
| <span data-ttu-id="178a1-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-173">1 1 0</span></span> | <span data-ttu-id="178a1-174">1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-174">1 1</span></span>   | <span data-ttu-id="178a1-175">1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-175">1 0</span></span>   | <span data-ttu-id="178a1-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-176">1 0 0</span></span> |
| <span data-ttu-id="178a1-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-177">1 1 1</span></span> | <span data-ttu-id="178a1-178">1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-178">1 1</span></span>   | <span data-ttu-id="178a1-179">1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-179">1 1</span></span>   | <span data-ttu-id="178a1-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-180">1 1 0</span></span> |

<span data-ttu-id="178a1-181">Ensuite, la valeur 0 est placée pour le premier élément avec un index vide à la colonne 0 du bloc B, puis 1 est placé dans B où le préfixe correspond (dans le premier cas, l’autre ligne avec les index 0 0).</span><span class="sxs-lookup"><span data-stu-id="178a1-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="178a1-182">Ensuite, un 1 est ajouté à la même ligne dans le bloc C, puis 0 pour le préfixe correspondant dans le bloc C.  Ce processus est répété, jusqu’à ce que tous les index aient été placés dans la colonne 0 des blocs B et C.</span><span class="sxs-lookup"><span data-stu-id="178a1-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="178a1-183">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="178a1-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="178a1-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-184">2 1 0</span></span> | <span data-ttu-id="178a1-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-185">2 1 0</span></span> | <span data-ttu-id="178a1-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-186">2 1 0</span></span> | <span data-ttu-id="178a1-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="178a1-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-188">0 0 0</span></span> | <span data-ttu-id="178a1-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-189">0 0 0</span></span> | <span data-ttu-id="178a1-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-190">0 0 0</span></span> | <span data-ttu-id="178a1-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-191">0 0 0</span></span> |
| <span data-ttu-id="178a1-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-192">0 0 1</span></span> | <span data-ttu-id="178a1-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-193">0 0 1</span></span> | <span data-ttu-id="178a1-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-194">0 1 1</span></span> | <span data-ttu-id="178a1-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-195">0 1 0</span></span> |
| <span data-ttu-id="178a1-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-196">0 1 0</span></span> | <span data-ttu-id="178a1-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-197">0 1 0</span></span> | <span data-ttu-id="178a1-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-198">0 1 0</span></span> | <span data-ttu-id="178a1-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-199">0 1 1</span></span> |
| <span data-ttu-id="178a1-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-200">0 1 1</span></span> | <span data-ttu-id="178a1-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-201">0 1 1</span></span> | <span data-ttu-id="178a1-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-202">1 0 1</span></span> | <span data-ttu-id="178a1-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-203">1 0 1</span></span> |
| <span data-ttu-id="178a1-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-204">1 0 0</span></span> | <span data-ttu-id="178a1-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-205">1 0 0</span></span> | <span data-ttu-id="178a1-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-206">1 1 0</span></span> | <span data-ttu-id="178a1-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-207">1 1 1</span></span> |
| <span data-ttu-id="178a1-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-208">1 0 1</span></span> | <span data-ttu-id="178a1-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-209">1 0 1</span></span> | <span data-ttu-id="178a1-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-210">0 0 1</span></span> | <span data-ttu-id="178a1-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="178a1-211">0 0 1</span></span> |
| <span data-ttu-id="178a1-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-212">1 1 0</span></span> | <span data-ttu-id="178a1-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-213">1 1 0</span></span> | <span data-ttu-id="178a1-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-214">1 0 0</span></span> | <span data-ttu-id="178a1-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="178a1-215">1 0 0</span></span> |
| <span data-ttu-id="178a1-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-216">1 1 1</span></span> | <span data-ttu-id="178a1-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-217">1 1 1</span></span> | <span data-ttu-id="178a1-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="178a1-218">1 1 1</span></span> | <span data-ttu-id="178a1-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="178a1-219">1 1 0</span></span> |

<span data-ttu-id="178a1-220">Nous pouvons lire trois nouvelles permutations à partir de la table :</span><span class="sxs-lookup"><span data-stu-id="178a1-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="178a1-221">$ \ pi_l $ avec les éléments d’un, images en B (à gauche)</span><span class="sxs-lookup"><span data-stu-id="178a1-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="178a1-222">$ \ pi_r $ avec des éléments dans D, images en C (à droite)</span><span class="sxs-lookup"><span data-stu-id="178a1-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="178a1-223">$ \pi' $ avec des éléments dans B, images en C (reste)</span><span class="sxs-lookup"><span data-stu-id="178a1-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="178a1-224">Notez que les valeurs de bit de conception ne changent pas dans $ \ pi_l $ et $ \ pi_r $ pour les index 1 et 2, et les valeurs de bit ne changent pas pour dans $ \ pi_ ' $ pour l’index 0.</span><span class="sxs-lookup"><span data-stu-id="178a1-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="178a1-225">Notez également que $ \ pi_l $ et $ \ pi_r $ doivent être auto-inverses.</span><span class="sxs-lookup"><span data-stu-id="178a1-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="178a1-226">Les permutations dérivées et retournées sont : Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] reste = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="178a1-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>