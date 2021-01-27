---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Opération PrepareSparseMultiConfigurationalState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 49b93d0f2447e9eee503bb6ee26aef46c4f5e3f2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98836060"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="374b9-102">Opération PrepareSparseMultiConfigurationalState</span><span class="sxs-lookup"><span data-stu-id="374b9-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="374b9-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="374b9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="374b9-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="374b9-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="374b9-105">La préparation de l’état d’évaluation de l’État multi-configuration est partiellement allouée par l’ajout d’une version d’évaluation initiale.</span><span class="sxs-lookup"><span data-stu-id="374b9-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="374b9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="374b9-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="374b9-107">initialStatePreparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="374b9-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="374b9-108">Unité pour préparer l’état initial de l’essai.</span><span class="sxs-lookup"><span data-stu-id="374b9-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="374b9-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="374b9-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="374b9-110">Indique l’état initial de l’essai représenté par l’amplitude de l’excitation et les index qubit sur lesquels l’excitation agit.</span><span class="sxs-lookup"><span data-stu-id="374b9-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="374b9-111">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="374b9-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="374b9-112">Qubits de Hamilton.</span><span class="sxs-lookup"><span data-stu-id="374b9-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="374b9-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="374b9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

