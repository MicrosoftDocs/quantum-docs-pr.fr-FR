---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Opération ApplyPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: 7f42d9cab2f80f8f826ad1268b050134f0540cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218221"
---
# <a name="applypauli-operation"></a><span data-ttu-id="9a0f5-102">Opération ApplyPauli</span><span class="sxs-lookup"><span data-stu-id="9a0f5-102">ApplyPauli operation</span></span>

<span data-ttu-id="9a0f5-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a0f5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a0f5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a0f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a0f5-105">À partir d’un opérateur qubit Pauli, applique l’opération correspondante à un registre.</span><span class="sxs-lookup"><span data-stu-id="9a0f5-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9a0f5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9a0f5-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="9a0f5-107">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="9a0f5-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="9a0f5-108">Opérateur Pauli qubit multiple représenté sous la forme d’un tableau d’opérateurs Pauli qubit uniques.</span><span class="sxs-lookup"><span data-stu-id="9a0f5-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9a0f5-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9a0f5-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9a0f5-110">Inscrivez-vous pour appliquer l’opération Pauli donnée sur.</span><span class="sxs-lookup"><span data-stu-id="9a0f5-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a0f5-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a0f5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

