---
uid: Microsoft.Quantum.Math.ModulusI
title: Fonction modulo
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708261"
---
# <a name="modulusi-function"></a><span data-ttu-id="5ddcc-102">Fonction modulo</span><span class="sxs-lookup"><span data-stu-id="5ddcc-102">ModulusI function</span></span>

<span data-ttu-id="5ddcc-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5ddcc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5ddcc-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ddcc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ddcc-105">Calcule le résidu canonique du `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="5ddcc-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="5ddcc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="5ddcc-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="5ddcc-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ddcc-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ddcc-108">Valeur de laquelle le résidu est calculé</span><span class="sxs-lookup"><span data-stu-id="5ddcc-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="5ddcc-109">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ddcc-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ddcc-110">Le modulo par lequel les résidus sont précédés doit être positif</span><span class="sxs-lookup"><span data-stu-id="5ddcc-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="5ddcc-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ddcc-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ddcc-112">Entier $r $ entre 0 et `modulus - 1` qui `value - r` est divisible par le modulo</span><span class="sxs-lookup"><span data-stu-id="5ddcc-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="5ddcc-113">Notes</span><span class="sxs-lookup"><span data-stu-id="5ddcc-113">Remarks</span></span>

<span data-ttu-id="5ddcc-114">Cette fonction se comporte différemment de la façon dont l’opérateur `%` se comporte en C# et Q # comme dans le résultat est toujours un entier positif compris entre 0 et `modulus - 1` , même si la valeur est négative.</span><span class="sxs-lookup"><span data-stu-id="5ddcc-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>