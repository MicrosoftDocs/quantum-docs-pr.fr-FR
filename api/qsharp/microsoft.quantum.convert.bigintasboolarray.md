---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 13ba5b6dbf477dd1a02f24da5b7aca9bdb30ad2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703033"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="2a871-102">BigIntAsBoolArray fonction)</span><span class="sxs-lookup"><span data-stu-id="2a871-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="2a871-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="2a871-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="2a871-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a871-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a871-105">Convertit un grand entier donné en un tableau de valeurs booléennes.</span><span class="sxs-lookup"><span data-stu-id="2a871-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="2a871-106">L’élément 0 du tableau est le bit le moins significatif du grand entier.</span><span class="sxs-lookup"><span data-stu-id="2a871-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="2a871-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="2a871-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2a871-108">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2a871-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="2a871-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2a871-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="2a871-110">Notes</span><span class="sxs-lookup"><span data-stu-id="2a871-110">Remarks</span></span>

<span data-ttu-id="2a871-111">Pour plus d’informations, consultez [constructeur BigInteger C#](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="2a871-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>