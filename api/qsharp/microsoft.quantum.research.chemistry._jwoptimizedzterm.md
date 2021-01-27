---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZTerm
title: Opération de _JWOptimizedZTerm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZTerm
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: fe68295748759a25c52f8e3c2efbc7570c9dcc1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848043"
---
# <a name="_jwoptimizedzterm-operation"></a><span data-ttu-id="e9787-102">Opération de _JWOptimizedZTerm</span><span class="sxs-lookup"><span data-stu-id="e9787-102">_JWOptimizedZTerm operation</span></span>

<span data-ttu-id="e9787-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e9787-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="e9787-104">Package : [Microsoft. Quantum. Research. chimie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e9787-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="e9787-105">Applique l’évolution de l’heure par un terme Z décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e9787-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e9787-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e9787-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="e9787-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e9787-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e9787-108">`GeneratorIndex` représentant un terme Z.</span><span class="sxs-lookup"><span data-stu-id="e9787-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="e9787-109">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9787-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9787-110">Durée de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="e9787-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="e9787-111">parityQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e9787-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e9787-112">Qubit qui détermine le signe de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="e9787-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e9787-113">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e9787-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e9787-114">Qubits de Hamilton.</span><span class="sxs-lookup"><span data-stu-id="e9787-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9787-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9787-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

