---
uid: Microsoft.Quantum.Intrinsic.T
title: Opération T
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 352ef2c1b15a46dea85c420fc6f1cfab0382e73a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198399"
---
# <a name="t-operation"></a><span data-ttu-id="c6de9-102">Opération T</span><span class="sxs-lookup"><span data-stu-id="c6de9-102">T operation</span></span>

<span data-ttu-id="c6de9-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="c6de9-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="c6de9-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c6de9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c6de9-105">Applique la porte T à un seul qubit.</span><span class="sxs-lookup"><span data-stu-id="c6de9-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c6de9-106">Description</span><span class="sxs-lookup"><span data-stu-id="c6de9-106">Description</span></span>

<span data-ttu-id="c6de9-107">Cette opération peut être simulée par la matrice \begin{align} T \mathrel{ : =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="c6de9-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="c6de9-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c6de9-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="c6de9-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="c6de9-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="c6de9-110">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c6de9-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c6de9-111">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="c6de9-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6de9-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6de9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

