---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Opération PrepareSparseMultiConfigurationalState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 1182f79a33784cdb49cb13db5cc97a0a45e59f9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703129"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="a9a5a-102">Opération PrepareSparseMultiConfigurationalState</span><span class="sxs-lookup"><span data-stu-id="a9a5a-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="a9a5a-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a9a5a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a9a5a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9a5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9a5a-105">La préparation de l’état d’évaluation de l’État multi-configuration est partiellement allouée par l’ajout d’une version d’évaluation initiale.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a9a5a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a9a5a-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="a9a5a-107">initialStatePreparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9a5a-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a9a5a-108">Unité pour préparer l’état initial de l’essai.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="a9a5a-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="a9a5a-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="a9a5a-110">Indique l’état initial de l’essai représenté par l’amplitude de l’excitation et les index qubit sur lesquels l’excitation agit.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a9a5a-111">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a9a5a-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a9a5a-112">Qubits de Hamilton.</span><span class="sxs-lookup"><span data-stu-id="a9a5a-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9a5a-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9a5a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

