---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702961"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="83204-102">IntAsBoolArray fonction)</span><span class="sxs-lookup"><span data-stu-id="83204-102">IntAsBoolArray function</span></span>

<span data-ttu-id="83204-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="83204-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="83204-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83204-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83204-105">Produit une représentation binaire d’un entier positif, à l’aide de la représentation avec primauté des octets de poids faible (Little-endian) pour le tableau retourné.</span><span class="sxs-lookup"><span data-stu-id="83204-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="83204-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="83204-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="83204-107">nombre : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83204-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83204-108">Entier positif à convertir en tableau de valeurs booléennes.</span><span class="sxs-lookup"><span data-stu-id="83204-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="83204-109">bits : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83204-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83204-110">Nombre de bits dans la représentation binaire de `number` .</span><span class="sxs-lookup"><span data-stu-id="83204-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="83204-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="83204-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="83204-112">Tableau de valeurs booléennes représentant `number` .</span><span class="sxs-lookup"><span data-stu-id="83204-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="83204-113">Notes</span><span class="sxs-lookup"><span data-stu-id="83204-113">Remarks</span></span>

<span data-ttu-id="83204-114">L’entrée `bits` doit être comprise entre 0 et 63.</span><span class="sxs-lookup"><span data-stu-id="83204-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="83204-115">L’entrée `number` doit être comprise entre 0 et $2 ^ {\texttt{bits}}-$1.</span><span class="sxs-lookup"><span data-stu-id="83204-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>