---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847258"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="5dfe0-102">BlockEncodingToReflection fonction)</span><span class="sxs-lookup"><span data-stu-id="5dfe0-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="5dfe0-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5dfe0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5dfe0-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5dfe0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5dfe0-105">Convertit un `BlockEncoding` en un équivalent `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="5dfe0-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="5dfe0-106">Autrement dit, étant donné un `BlockEncoding` $U unitaire $ qui encode un opérateur $H $ d’intérêt, le convertit en un `BlockEncodingReflection` $U' $ qui encode le même opérateur, mais satisfait également $U' ^ \Dagger = U' $.</span><span class="sxs-lookup"><span data-stu-id="5dfe0-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="5dfe0-107">Cela augmente la taille du Registre auxiliaire de $U $ par un qubit.</span><span class="sxs-lookup"><span data-stu-id="5dfe0-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="5dfe0-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="5dfe0-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="5dfe0-109">blockEncoding : [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="5dfe0-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="5dfe0-110">`BlockEncoding`$U unitaire $ à convertir en réflexion.</span><span class="sxs-lookup"><span data-stu-id="5dfe0-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="5dfe0-111">Sortie : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="5dfe0-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="5dfe0-112">Un $U unitaire' $ agit conjointement sur `a` les registres et `s` qui encodent le bloc $H $, et satisfont $U' ^ \Dagger = U' $.</span><span class="sxs-lookup"><span data-stu-id="5dfe0-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="5dfe0-113">Notes</span><span class="sxs-lookup"><span data-stu-id="5dfe0-113">Remarks</span></span>

<span data-ttu-id="5dfe0-114">Cela augmente la taille du Registre auxiliaire de $U $ par un qubit.</span><span class="sxs-lookup"><span data-stu-id="5dfe0-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="5dfe0-115">Références</span><span class="sxs-lookup"><span data-stu-id="5dfe0-115">References</span></span>

- <span data-ttu-id="5dfe0-116">Simulation de la Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="5dfe0-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="5dfe0-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5dfe0-117">See Also</span></span>

- [<span data-ttu-id="5dfe0-118">Microsoft. Quantum. simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="5dfe0-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="5dfe0-119">Microsoft. Quantum. simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="5dfe0-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)