---
uid: Microsoft.Quantum.Math.ModulusI
title: Fonction modulo
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227775"
---
# <a name="modulusi-function"></a><span data-ttu-id="72b28-102">Fonction modulo</span><span class="sxs-lookup"><span data-stu-id="72b28-102">ModulusI function</span></span>

<span data-ttu-id="72b28-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="72b28-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="72b28-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72b28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72b28-105">Calcule le résidu canonique du `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="72b28-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="72b28-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="72b28-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="72b28-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72b28-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72b28-108">Valeur de laquelle le résidu est calculé</span><span class="sxs-lookup"><span data-stu-id="72b28-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="72b28-109">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72b28-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72b28-110">Le modulo par lequel les résidus sont précédés doit être positif</span><span class="sxs-lookup"><span data-stu-id="72b28-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="72b28-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72b28-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72b28-112">Entier $r $ entre 0 et `modulus - 1` qui `value - r` est divisible par le modulo</span><span class="sxs-lookup"><span data-stu-id="72b28-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="72b28-113">Notes</span><span class="sxs-lookup"><span data-stu-id="72b28-113">Remarks</span></span>

<span data-ttu-id="72b28-114">Cette fonction se comporte différemment de la façon dont l’opérateur `%` se comporte en C# et Q # comme dans le résultat est toujours un entier positif compris entre 0 et `modulus - 1` , même si la valeur est négative.</span><span class="sxs-lookup"><span data-stu-id="72b28-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>