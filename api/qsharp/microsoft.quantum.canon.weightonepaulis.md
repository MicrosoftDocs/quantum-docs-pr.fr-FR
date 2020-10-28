---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703708"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="e71fd-102">WeightOnePaulis fonction)</span><span class="sxs-lookup"><span data-stu-id="e71fd-102">WeightOnePaulis function</span></span>

<span data-ttu-id="e71fd-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e71fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e71fd-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e71fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e71fd-105">Retourne un tableau de tous les opérateurs Weight-1 Pauli sur un nombre donné de qubits.</span><span class="sxs-lookup"><span data-stu-id="e71fd-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="e71fd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e71fd-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="e71fd-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e71fd-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e71fd-108">Nombre de qubits sur lesquels les opérateurs Pauli retournés sont définis.</span><span class="sxs-lookup"><span data-stu-id="e71fd-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="e71fd-109">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="e71fd-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="e71fd-110">Tableau d’opérateurs Pauli qubit, chacun d’eux étant représenté sous la forme d’un tableau de longueur `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="e71fd-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>