---
uid: Microsoft.Quantum.Math.ModulusL
title: Fonction modulo
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194931"
---
# <a name="modulusl-function"></a><span data-ttu-id="c8f86-102">Fonction modulo</span><span class="sxs-lookup"><span data-stu-id="c8f86-102">ModulusL function</span></span>

<span data-ttu-id="c8f86-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c8f86-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c8f86-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8f86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8f86-105">Calcule le résidu canonique du `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="c8f86-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="c8f86-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c8f86-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="c8f86-107">valeur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8f86-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8f86-108">Valeur de laquelle le résidu est calculé</span><span class="sxs-lookup"><span data-stu-id="c8f86-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="c8f86-109">modulo : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8f86-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8f86-110">Le modulo par lequel les résidus sont précédés doit être positif</span><span class="sxs-lookup"><span data-stu-id="c8f86-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="c8f86-111">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8f86-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8f86-112">Entier $r $ entre 0 et `modulus - 1` qui `value - r` est divisible par le modulo</span><span class="sxs-lookup"><span data-stu-id="c8f86-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="c8f86-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c8f86-113">Remarks</span></span>

<span data-ttu-id="c8f86-114">Cette fonction se comporte différemment de la façon dont l’opérateur `%` se comporte en C# et Q # comme dans le résultat est toujours un entier positif compris entre 0 et `modulus - 1` , même si la valeur est négative.</span><span class="sxs-lookup"><span data-stu-id="c8f86-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>