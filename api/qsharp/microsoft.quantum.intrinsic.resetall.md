---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: Opération ResetAll
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: d22ce607e8e5cb3a1c041dc1973875f2a0777d2b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198688"
---
# <a name="resetall-operation"></a><span data-ttu-id="d1451-102">Opération ResetAll</span><span class="sxs-lookup"><span data-stu-id="d1451-102">ResetAll operation</span></span>

<span data-ttu-id="d1451-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d1451-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d1451-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d1451-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d1451-105">À partir d’un tableau de qubits, mesurez-les et assurez-vous qu’ils sont dans l’État | 0 ⟩, de sorte qu’ils puissent être libérés en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="d1451-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d1451-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d1451-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="d1451-107">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d1451-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d1451-108">Tableau de qubits dont les États doivent être réinitialisés à $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d1451-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1451-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1451-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

