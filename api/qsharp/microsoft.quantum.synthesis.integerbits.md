---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706427"
---
# <a name="integerbits-function"></a><span data-ttu-id="e7332-102">IntegerBits fonction)</span><span class="sxs-lookup"><span data-stu-id="e7332-102">IntegerBits function</span></span>

<span data-ttu-id="e7332-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e7332-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e7332-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e7332-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e7332-105">Retourne toutes les positions dans lesquelles les bits d’un entier sont définis.</span><span class="sxs-lookup"><span data-stu-id="e7332-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="e7332-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e7332-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="e7332-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7332-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7332-108">Nombre non négatif.</span><span class="sxs-lookup"><span data-stu-id="e7332-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="e7332-109">Longueur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7332-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7332-110">Nombre de bits dans l’expansion binaire de `value` .</span><span class="sxs-lookup"><span data-stu-id="e7332-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="e7332-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e7332-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e7332-112">Tableau qui contient toutes les positions de bits (à partir de 0) qui sont égales à 1 dans l’expansion binaire de la prise `value` en compte de tous les bits jusqu’à la position `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="e7332-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="e7332-113">Toutes les positions sont classées dans le tableau par position dans un ordre de croisement.</span><span class="sxs-lookup"><span data-stu-id="e7332-113">All positions are ordered in the array by position in an increasing order.</span></span>