---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Opération de réinitialisation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818640"
---
# <a name="reset-operation"></a><span data-ttu-id="537e1-102">Opération de réinitialisation</span><span class="sxs-lookup"><span data-stu-id="537e1-102">Reset operation</span></span>

<span data-ttu-id="537e1-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="537e1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="537e1-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="537e1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="537e1-105">Étant donné un qubit unique, le mesure et s’assure qu’il est dans l’État | 0 ⟩, de sorte qu’il peut être libéré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="537e1-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="537e1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="537e1-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="537e1-107">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="537e1-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="537e1-108">Qubit dont l’État doit être réinitialisé à $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="537e1-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="537e1-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="537e1-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

