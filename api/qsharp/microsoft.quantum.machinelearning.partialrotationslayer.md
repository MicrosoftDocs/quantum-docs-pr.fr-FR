---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ade0640b07f633982e98d5d02239fa205909bcce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196240"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="3c4d6-102">PartialRotationsLayer fonction)</span><span class="sxs-lookup"><span data-stu-id="3c4d6-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="3c4d6-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3c4d6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3c4d6-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3c4d6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3c4d6-105">Retourne un tableau de rotations à qubit unique le long d’un axe donné, paramétrable par des paramètres de modèle distincts.</span><span class="sxs-lookup"><span data-stu-id="3c4d6-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="3c4d6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3c4d6-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="3c4d6-107">idxsQubits : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3c4d6-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3c4d6-108">Index pour le qubits à utiliser comme cibles pour chaque rotation.</span><span class="sxs-lookup"><span data-stu-id="3c4d6-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="3c4d6-109">axe : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="3c4d6-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="3c4d6-110">Axe de rotation pour chaque rotation dans la couche donnée.</span><span class="sxs-lookup"><span data-stu-id="3c4d6-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="3c4d6-111">Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="3c4d6-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="3c4d6-112">Tableau de rotations contrôlées sur l’axe donné, une sur chaque `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="3c4d6-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>