---
uid: Microsoft.Quantum.Measurement.MultiM
title: Opération multifacteur
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226993"
---
# <a name="multim-operation"></a><span data-ttu-id="ac3a0-102">Opération multifacteur</span><span class="sxs-lookup"><span data-stu-id="ac3a0-102">MultiM operation</span></span>

<span data-ttu-id="ac3a0-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="ac3a0-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="ac3a0-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac3a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac3a0-105">Mesure chaque qubit dans un tableau donné de manière standard.</span><span class="sxs-lookup"><span data-stu-id="ac3a0-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="ac3a0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ac3a0-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="ac3a0-107">cibles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ac3a0-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ac3a0-108">Tableau de qubits à mesurer.</span><span class="sxs-lookup"><span data-stu-id="ac3a0-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ac3a0-109">Sortie : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="ac3a0-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="ac3a0-110">Tableau de résultats de mesure.</span><span class="sxs-lookup"><span data-stu-id="ac3a0-110">An array of measurement results.</span></span>