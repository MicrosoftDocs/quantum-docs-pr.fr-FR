---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: a3658bbf62068c9eea2d9b763cbff5596f426135
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854973"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="d48a5-102">LocalRotationsLayer fonction)</span><span class="sxs-lookup"><span data-stu-id="d48a5-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="d48a5-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d48a5-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d48a5-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d48a5-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d48a5-105">Retourne un tableau de rotations non contrôlées (qubit simples) le long d’un axe donné, avec une rotation pour chaque qubit dans un registre, paramétrable par des paramètres de modèle distincts.</span><span class="sxs-lookup"><span data-stu-id="d48a5-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="d48a5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d48a5-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="d48a5-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d48a5-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d48a5-108">Nombre de qubits traités par la couche donnée.</span><span class="sxs-lookup"><span data-stu-id="d48a5-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="d48a5-109">axe : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="d48a5-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="d48a5-110">Axe de rotation pour chaque rotation dans la couche donnée.</span><span class="sxs-lookup"><span data-stu-id="d48a5-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="d48a5-111">Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="d48a5-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="d48a5-112">Tableau de rotations contrôlées sur l’axe donné, une sur chaque `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="d48a5-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>