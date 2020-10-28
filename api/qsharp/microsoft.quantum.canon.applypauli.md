---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Opération ApplyPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705110"
---
# <a name="applypauli-operation"></a><span data-ttu-id="a27bc-102">Opération ApplyPauli</span><span class="sxs-lookup"><span data-stu-id="a27bc-102">ApplyPauli operation</span></span>

<span data-ttu-id="a27bc-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a27bc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a27bc-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a27bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a27bc-105">À partir d’un opérateur qubit Pauli, applique l’opération correspondante à un registre.</span><span class="sxs-lookup"><span data-stu-id="a27bc-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a27bc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a27bc-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="a27bc-107">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a27bc-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a27bc-108">Opérateur Pauli qubit multiple représenté sous la forme d’un tableau d’opérateurs Pauli qubit uniques.</span><span class="sxs-lookup"><span data-stu-id="a27bc-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a27bc-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a27bc-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a27bc-110">Inscrivez-vous pour appliquer l’opération Pauli donnée sur.</span><span class="sxs-lookup"><span data-stu-id="a27bc-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a27bc-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a27bc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

