---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 8aeea795ef5409339e8a1b39c3ffcfaf29d675b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851967"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="6e166-102">WeightOnePaulis fonction)</span><span class="sxs-lookup"><span data-stu-id="6e166-102">WeightOnePaulis function</span></span>

<span data-ttu-id="6e166-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6e166-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6e166-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e166-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e166-105">Retourne un tableau de tous les opérateurs Weight-1 Pauli sur un nombre donné de qubits.</span><span class="sxs-lookup"><span data-stu-id="6e166-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="6e166-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6e166-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="6e166-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e166-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e166-108">Nombre de qubits sur lesquels les opérateurs Pauli retournés sont définis.</span><span class="sxs-lookup"><span data-stu-id="6e166-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="6e166-109">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="6e166-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="6e166-110">Tableau d’opérateurs Pauli qubit, chacun d’eux étant représenté sous la forme d’un tableau de longueur `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="6e166-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>