---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: opération de _prepareTrialStateWrapper
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: bfd7b9ce8e8b2c8f322d676c640f8c2488655516
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703093"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="530ed-102">opération de _prepareTrialStateWrapper</span><span class="sxs-lookup"><span data-stu-id="530ed-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="530ed-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="530ed-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="530ed-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="530ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="530ed-105">Wrapper privé autour de PrepareTrialState pour le rendre compatible avec EstimateFrequencyA en définissant un voisint.</span><span class="sxs-lookup"><span data-stu-id="530ed-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="530ed-106">EstimateFrequencyA dispose d’une fonctionnalité d’émulation intégrée lors du ciblage du QuantumSimulator, ce qui accélère son exécution.</span><span class="sxs-lookup"><span data-stu-id="530ed-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="530ed-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="530ed-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="530ed-108">inputState : ([int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span><span class="sxs-lookup"><span data-stu-id="530ed-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="530ed-109">L' Jordan-Wigner entrée nécessaire à l’exécution de PrepareTrialState.</span><span class="sxs-lookup"><span data-stu-id="530ed-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="530ed-110">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="530ed-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="530ed-111">Un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="530ed-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="530ed-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="530ed-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

