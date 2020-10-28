---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Opération SetToBasisState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708939"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="15d19-102">Opération SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="15d19-102">SetToBasisState operation</span></span>

<span data-ttu-id="15d19-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="15d19-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="15d19-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15d19-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15d19-105">Définit un qubit sur un état de base donné en mesurant le qubit et en appliquant un retournement binaire, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="15d19-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="15d19-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="15d19-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="15d19-107">desired __: <Result> non valide__</span><span class="sxs-lookup"><span data-stu-id="15d19-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="15d19-108">État de base auquel le qubit doit être défini.</span><span class="sxs-lookup"><span data-stu-id="15d19-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="15d19-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="15d19-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="15d19-110">Qubit dont l’État doit être défini.</span><span class="sxs-lookup"><span data-stu-id="15d19-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15d19-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15d19-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="15d19-112">Notes</span><span class="sxs-lookup"><span data-stu-id="15d19-112">Remarks</span></span>

<span data-ttu-id="15d19-113">Comme un invariant de cette opération, l’appel de `M(q)` juste après `SetToBasisState(result, q)` retourne `result` .</span><span class="sxs-lookup"><span data-stu-id="15d19-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>