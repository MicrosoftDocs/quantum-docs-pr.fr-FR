---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708423"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="82652-102">LocalRotationsLayer fonction)</span><span class="sxs-lookup"><span data-stu-id="82652-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="82652-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="82652-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="82652-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82652-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82652-105">Retourne un tableau de rotations non contrôlées (qubit simples) le long d’un axe donné, avec une rotation pour chaque qubit dans un registre, paramétrable par des paramètres de modèle distincts.</span><span class="sxs-lookup"><span data-stu-id="82652-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="82652-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="82652-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="82652-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82652-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82652-108">Nombre de qubits traités par la couche donnée.</span><span class="sxs-lookup"><span data-stu-id="82652-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="82652-109">axe : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="82652-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="82652-110">Axe de rotation pour chaque rotation dans la couche donnée.</span><span class="sxs-lookup"><span data-stu-id="82652-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="82652-111">Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="82652-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="82652-112">Tableau de rotations contrôlées sur l’axe donné, une sur chaque `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="82652-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>