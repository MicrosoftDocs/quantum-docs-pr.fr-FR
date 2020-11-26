---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5421765e36ef3e8e744e118206dafcb2bb582cc2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211931"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="0d2b9-102">CyclicEntanglingLayer fonction)</span><span class="sxs-lookup"><span data-stu-id="0d2b9-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="0d2b9-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0d2b9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0d2b9-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0d2b9-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="0d2b9-105">Retourne un tableau de rotations contrôlées de façon unique le long d’un axe donné, organisées de façon cyclique sur un registre de qubits et paramétrables par des paramètres de modèle distincts.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="0d2b9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0d2b9-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="0d2b9-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0d2b9-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0d2b9-108">Nombre de qubits traités par la couche donnée.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="0d2b9-109">axe : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="0d2b9-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="0d2b9-110">Axe de rotation pour chaque rotation dans la couche donnée.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="0d2b9-111">STRIDE : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0d2b9-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0d2b9-112">Séparation entre les index cible et de contrôle pour chaque rotation.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="0d2b9-113">Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="0d2b9-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="0d2b9-114">Tableau de rotations contrôlées par deux qubit disposées de façon cyclique sur un registre de `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>