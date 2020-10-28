---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: Opération de _JWOptimizedZZTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 824918e06e54e31834019a396b310bbaa6beeb46
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708126"
---
# <a name="_jwoptimizedzzterm-operation"></a><span data-ttu-id="82feb-102">Opération de _JWOptimizedZZTerm</span><span class="sxs-lookup"><span data-stu-id="82feb-102">_JWOptimizedZZTerm operation</span></span>

<span data-ttu-id="82feb-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="82feb-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="82feb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82feb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82feb-105">Applique l’évolution de l’heure par un terme ZZ décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="82feb-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="82feb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="82feb-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="82feb-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="82feb-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="82feb-108">`GeneratorIndex` représentant un terme ZZ.</span><span class="sxs-lookup"><span data-stu-id="82feb-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="82feb-109">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="82feb-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="82feb-110">Durée de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="82feb-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="82feb-111">parityQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="82feb-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="82feb-112">Qubit qui détermine le signe de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="82feb-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="82feb-113">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="82feb-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="82feb-114">Qubits de Hamilton.</span><span class="sxs-lookup"><span data-stu-id="82feb-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82feb-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82feb-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

