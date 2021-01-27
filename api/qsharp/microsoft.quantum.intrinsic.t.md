---
uid: Microsoft.Quantum.Intrinsic.T
title: Opération T
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: bee252d9905aed26f6bf663f895e464e38073f44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817512"
---
# <a name="t-operation"></a><span data-ttu-id="abf02-102">Opération T</span><span class="sxs-lookup"><span data-stu-id="abf02-102">T operation</span></span>

<span data-ttu-id="abf02-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="abf02-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="abf02-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="abf02-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="abf02-105">Applique la porte T à un seul qubit.</span><span class="sxs-lookup"><span data-stu-id="abf02-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="abf02-106">Description</span><span class="sxs-lookup"><span data-stu-id="abf02-106">Description</span></span>

<span data-ttu-id="abf02-107">Cette opération peut être simulée par la matrice \begin{align} T \mathrel{ : =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="abf02-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="abf02-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="abf02-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="abf02-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="abf02-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="abf02-110">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="abf02-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="abf02-111">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="abf02-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="abf02-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="abf02-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

