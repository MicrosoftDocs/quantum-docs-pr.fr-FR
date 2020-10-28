---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: OptimizedTrotterStepOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f78d80f7ab71f4fc759d8045c9a134d7178aaa15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701803"
---
# <a name="optimizedtrottersteporacle-function"></a><span data-ttu-id="c3bc6-102">OptimizedTrotterStepOracle fonction)</span><span class="sxs-lookup"><span data-stu-id="c3bc6-102">OptimizedTrotterStepOracle function</span></span>

<span data-ttu-id="c3bc6-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c3bc6-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c3bc6-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3bc6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3bc6-105">Retourne l’opération de l’étape Trotter optimisée et les paramètres nécessaires pour l’exécuter.</span><span class="sxs-lookup"><span data-stu-id="c3bc6-105">Returns optimized Trotter step operation and the parameters necessary to run it.</span></span>

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="c3bc6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c3bc6-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="c3bc6-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="c3bc6-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="c3bc6-108">Hamilton, décrit par `JordanWignerEncodingData` format.</span><span class="sxs-lookup"><span data-stu-id="c3bc6-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="c3bc6-109">trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c3bc6-109">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c3bc6-110">Taille d’étape de l’intégrateur trotter.</span><span class="sxs-lookup"><span data-stu-id="c3bc6-110">Step size of Trotter integrator.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="c3bc6-111">trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3bc6-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3bc6-112">Ordre de l’intégrateur trotter.</span><span class="sxs-lookup"><span data-stu-id="c3bc6-112">Order of Trotter integrator.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="c3bc6-113">Sortie : ([int](xref:microsoft.quantum.lang-ref.int), ([double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL))</span><span class="sxs-lookup"><span data-stu-id="c3bc6-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="c3bc6-114">Un tuple où : `Int` est le nombre d’qubits alloués, `Double` est `1.0/trotterStepSize` , et l’opération est l’étape trotter.</span><span class="sxs-lookup"><span data-stu-id="c3bc6-114">A tuple where: `Int` is the number of qubits allocated, `Double` is `1.0/trotterStepSize`, and the operation is the Trotter step.</span></span>