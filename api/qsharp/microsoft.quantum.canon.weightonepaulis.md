---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204536"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="eeabc-102">WeightOnePaulis fonction)</span><span class="sxs-lookup"><span data-stu-id="eeabc-102">WeightOnePaulis function</span></span>

<span data-ttu-id="eeabc-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eeabc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eeabc-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eeabc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eeabc-105">Retourne un tableau de tous les opérateurs Weight-1 Pauli sur un nombre donné de qubits.</span><span class="sxs-lookup"><span data-stu-id="eeabc-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="eeabc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="eeabc-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="eeabc-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eeabc-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eeabc-108">Nombre de qubits sur lesquels les opérateurs Pauli retournés sont définis.</span><span class="sxs-lookup"><span data-stu-id="eeabc-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="eeabc-109">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="eeabc-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="eeabc-110">Tableau d’opérateurs Pauli qubit, chacun d’eux étant représenté sous la forme d’un tableau de longueur `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="eeabc-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>