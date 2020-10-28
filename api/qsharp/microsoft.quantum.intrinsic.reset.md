---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Opération de réinitialisation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707110"
---
# <a name="reset-operation"></a><span data-ttu-id="fff81-102">Opération de réinitialisation</span><span class="sxs-lookup"><span data-stu-id="fff81-102">Reset operation</span></span>

<span data-ttu-id="fff81-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="fff81-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="fff81-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fff81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fff81-105">Étant donné un qubit unique, le mesure et s’assure qu’il est dans l’État | 0 ⟩, de sorte qu’il peut être libéré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="fff81-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="fff81-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fff81-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="fff81-107">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fff81-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fff81-108">Qubit dont l’État doit être réinitialisé à $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="fff81-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fff81-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fff81-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

