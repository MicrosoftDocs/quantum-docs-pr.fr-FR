---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833301"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="4bf54-102">IntAsBoolArray fonction)</span><span class="sxs-lookup"><span data-stu-id="4bf54-102">IntAsBoolArray function</span></span>

<span data-ttu-id="4bf54-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4bf54-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4bf54-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4bf54-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4bf54-105">Produit une représentation binaire d’un entier non négatif, à l’aide de la représentation avec primauté des octets de poids faible (Little-endian) pour le tableau retourné.</span><span class="sxs-lookup"><span data-stu-id="4bf54-105">Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="4bf54-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4bf54-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="4bf54-107">nombre : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4bf54-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4bf54-108">Entier non négatif à convertir en tableau de valeurs booléennes.</span><span class="sxs-lookup"><span data-stu-id="4bf54-108">A non-negative integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="4bf54-109">bits : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4bf54-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4bf54-110">Nombre de bits dans la représentation binaire de `number` .</span><span class="sxs-lookup"><span data-stu-id="4bf54-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4bf54-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4bf54-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4bf54-112">Tableau de valeurs booléennes représentant `number` .</span><span class="sxs-lookup"><span data-stu-id="4bf54-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4bf54-113">Notes</span><span class="sxs-lookup"><span data-stu-id="4bf54-113">Remarks</span></span>

<span data-ttu-id="4bf54-114">L’entrée `bits` doit être comprise entre 0 et 63.</span><span class="sxs-lookup"><span data-stu-id="4bf54-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="4bf54-115">L’entrée `number` doit être comprise entre 0 et $2 ^ {\texttt{bits}}-$1.</span><span class="sxs-lookup"><span data-stu-id="4bf54-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>