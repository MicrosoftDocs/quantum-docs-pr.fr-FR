---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQTerm_
title: Opération _ApplyJordanWignerPQTerm_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQTerm_
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 8a9b41e17bcc46c5aff2b18455e1eac25620fe35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703528"
---
# <a name="_applyjordanwignerpqterm_-operation"></a><span data-ttu-id="13fb9-102">Opération _ApplyJordanWignerPQTerm_</span><span class="sxs-lookup"><span data-stu-id="13fb9-102">_ApplyJordanWignerPQTerm_ operation</span></span>

<span data-ttu-id="13fb9-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="13fb9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="13fb9-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13fb9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13fb9-105">Applique l’évolution de l’heure par un terme PQ décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="13fb9-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, extraParityQubits : Qubit[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="13fb9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="13fb9-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="13fb9-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="13fb9-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="13fb9-108">`GeneratorIndex` représentant un terme PQ.</span><span class="sxs-lookup"><span data-stu-id="13fb9-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="13fb9-109">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="13fb9-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="13fb9-110">Durée de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="13fb9-110">Duration of time-evolution.</span></span>


### <a name="extraparityqubits--qubit"></a><span data-ttu-id="13fb9-111">extraParityQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="13fb9-111">extraParityQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="13fb9-112">Qubits de parité facultatif qui inversent le signe de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="13fb9-112">Optional parity qubits that flip the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="13fb9-113">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="13fb9-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="13fb9-114">Qubits de Hamilton.</span><span class="sxs-lookup"><span data-stu-id="13fb9-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="13fb9-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13fb9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

