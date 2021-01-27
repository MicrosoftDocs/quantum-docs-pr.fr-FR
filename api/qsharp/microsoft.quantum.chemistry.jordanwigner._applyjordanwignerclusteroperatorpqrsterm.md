---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQRSTerm
title: Opération de _ApplyJordanWignerClusterOperatorPQRSTerm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQRSTerm
qsharp.summary: Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: f5f77c102596c26100c85eaac42f5f88848e4550
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839588"
---
# <a name="_applyjordanwignerclusteroperatorpqrsterm-operation"></a><span data-ttu-id="e8c6c-102">Opération de _ApplyJordanWignerClusterOperatorPQRSTerm</span><span class="sxs-lookup"><span data-stu-id="e8c6c-102">_ApplyJordanWignerClusterOperatorPQRSTerm operation</span></span>

<span data-ttu-id="e8c6c-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e8c6c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e8c6c-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e8c6c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="e8c6c-105">Applique l’évolution du temps par un opérateur de cluster PQRS terme décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e8c6c-105">Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQRSTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e8c6c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e8c6c-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="e8c6c-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e8c6c-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e8c6c-108">`GeneratorIndex` représentant un terme PQRS opérateur de cluster.</span><span class="sxs-lookup"><span data-stu-id="e8c6c-108">`GeneratorIndex` representing a cluster operator PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="e8c6c-109">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8c6c-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8c6c-110">Durée de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="e8c6c-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e8c6c-111">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e8c6c-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e8c6c-112">Qubits de Hamilton.</span><span class="sxs-lookup"><span data-stu-id="e8c6c-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8c6c-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8c6c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

