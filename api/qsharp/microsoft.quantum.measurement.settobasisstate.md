---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Opération SetToBasisState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194149"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="25187-102">Opération SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="25187-102">SetToBasisState operation</span></span>

<span data-ttu-id="25187-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="25187-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="25187-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="25187-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="25187-105">Définit un qubit sur un état de base donné en mesurant le qubit et en appliquant un retournement binaire, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="25187-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="25187-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="25187-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="25187-107">desired __: <Result> non valide__</span><span class="sxs-lookup"><span data-stu-id="25187-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="25187-108">État de base auquel le qubit doit être défini.</span><span class="sxs-lookup"><span data-stu-id="25187-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="25187-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="25187-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="25187-110">Qubit dont l’État doit être défini.</span><span class="sxs-lookup"><span data-stu-id="25187-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25187-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25187-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="25187-112">Notes</span><span class="sxs-lookup"><span data-stu-id="25187-112">Remarks</span></span>

<span data-ttu-id="25187-113">Comme un invariant de cette opération, l’appel de `M(q)` juste après `SetToBasisState(result, q)` retourne `result` .</span><span class="sxs-lookup"><span data-stu-id="25187-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>