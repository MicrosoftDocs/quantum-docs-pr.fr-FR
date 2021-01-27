---
uid: Microsoft.Quantum.Math.ModL
title: ModL fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: f044ae16d93d31d0f28f5fcf076cff2bfef62eb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846840"
---
# <a name="modl-function"></a><span data-ttu-id="655fa-102">ModL fonction)</span><span class="sxs-lookup"><span data-stu-id="655fa-102">ModL function</span></span>

<span data-ttu-id="655fa-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="655fa-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="655fa-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="655fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="655fa-105">Retourne le modulo d’un nombre par rapport à un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="655fa-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="655fa-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="655fa-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="655fa-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="655fa-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="655fa-108">Entrée $a $ dont le modulo doit être retourné.</span><span class="sxs-lookup"><span data-stu-id="655fa-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="655fa-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="655fa-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="655fa-110">Nombre par rapport auquel le modulo de $a $ doit être retourné.</span><span class="sxs-lookup"><span data-stu-id="655fa-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="655fa-111">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="655fa-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="655fa-112">Le modulo $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="655fa-112">The modulus $a \bmod b$.</span></span>