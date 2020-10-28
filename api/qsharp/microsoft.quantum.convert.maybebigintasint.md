---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: b91912f6f669afad888e71174fef6e2e6f8e7156
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702952"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="9123b-102">MaybeBigIntAsInt fonction)</span><span class="sxs-lookup"><span data-stu-id="9123b-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="9123b-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="9123b-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="9123b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9123b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9123b-105">Convertit un grand entier donné en un entier équivalent, si possible.</span><span class="sxs-lookup"><span data-stu-id="9123b-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="9123b-106">La fonction retourne une paire de l’entier résultant et un indicateur booléen qui a la valeur true, si et seulement si la conversion était possible.</span><span class="sxs-lookup"><span data-stu-id="9123b-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="9123b-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="9123b-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9123b-108">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9123b-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="9123b-109">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool))</span><span class="sxs-lookup"><span data-stu-id="9123b-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="9123b-110">Notes</span><span class="sxs-lookup"><span data-stu-id="9123b-110">Remarks</span></span>

<span data-ttu-id="9123b-111">Pour plus d’informations, consultez [constructeur BigInteger C#](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="9123b-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>