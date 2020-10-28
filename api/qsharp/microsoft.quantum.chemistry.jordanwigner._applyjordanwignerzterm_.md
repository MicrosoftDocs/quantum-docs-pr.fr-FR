---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: Opération _ApplyJordanWignerZTerm_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: f42c2ba7570f32d3f26ff82dd4a0ee6f9677fa30
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703507"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="1e52e-102">Opération _ApplyJordanWignerZTerm_</span><span class="sxs-lookup"><span data-stu-id="1e52e-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="1e52e-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1e52e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1e52e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e52e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e52e-105">Applique l’évolution de l’heure par un terme Z décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="1e52e-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1e52e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1e52e-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="1e52e-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="1e52e-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="1e52e-108">`GeneratorIndex` représentant un terme Z.</span><span class="sxs-lookup"><span data-stu-id="1e52e-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="1e52e-109">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1e52e-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1e52e-110">Durée de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="1e52e-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1e52e-111">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1e52e-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1e52e-112">Qubits de Hamilton.</span><span class="sxs-lookup"><span data-stu-id="1e52e-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e52e-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e52e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

