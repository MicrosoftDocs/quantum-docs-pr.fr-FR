---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707823"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="d7f67-102">BlockEncodingToReflection fonction)</span><span class="sxs-lookup"><span data-stu-id="d7f67-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="d7f67-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d7f67-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d7f67-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7f67-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7f67-105">Convertit un `BlockEncoding` en un équivalent `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="d7f67-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="d7f67-106">Autrement dit, étant donné un `BlockEncoding` $U unitaire $ qui encode un opérateur $H $ d’intérêt, le convertit en un `BlockEncodingReflection` $U' $ qui encode le même opérateur, mais satisfait également $U' ^ \Dagger = U' $.</span><span class="sxs-lookup"><span data-stu-id="d7f67-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="d7f67-107">Cela augmente la taille du Registre auxiliaire de $U $ par un qubit.</span><span class="sxs-lookup"><span data-stu-id="d7f67-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="d7f67-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="d7f67-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="d7f67-109">blockEncoding : [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="d7f67-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="d7f67-110">`BlockEncoding`$U unitaire $ à convertir en réflexion.</span><span class="sxs-lookup"><span data-stu-id="d7f67-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="d7f67-111">Sortie : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="d7f67-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="d7f67-112">Un $U unitaire' $ agit conjointement sur `a` les registres et `s` qui encodent le bloc $H $, et satisfont $U' ^ \Dagger = U' $.</span><span class="sxs-lookup"><span data-stu-id="d7f67-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7f67-113">Notes</span><span class="sxs-lookup"><span data-stu-id="d7f67-113">Remarks</span></span>

<span data-ttu-id="d7f67-114">Cela augmente la taille du Registre auxiliaire de $U $ par un qubit.</span><span class="sxs-lookup"><span data-stu-id="d7f67-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="d7f67-115">Références</span><span class="sxs-lookup"><span data-stu-id="d7f67-115">References</span></span>

- <span data-ttu-id="d7f67-116">Simulation de la Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="d7f67-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="d7f67-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7f67-117">See Also</span></span>

- [<span data-ttu-id="d7f67-118">Microsoft. Quantum. simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="d7f67-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="d7f67-119">Microsoft. Quantum. simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="d7f67-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)