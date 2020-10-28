---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicC
title: Opération ApplyConditionallyIntrinsicC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 54367d89636eb69462040e83cc3c4b6a9f734c0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706622"
---
# <a name="applyconditionallyintrinsicc-operation"></a><span data-ttu-id="4c900-102">Opération ApplyConditionallyIntrinsicC</span><span class="sxs-lookup"><span data-stu-id="4c900-102">ApplyConditionallyIntrinsicC operation</span></span>

<span data-ttu-id="4c900-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="4c900-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="4c900-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c900-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicC (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl), onNonEqualOp : (Unit => Unit is Ctl)) : Unit
```


## <a name="input"></a><span data-ttu-id="4c900-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="4c900-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="4c900-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="4c900-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="4c900-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="4c900-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit-ctl"></a><span data-ttu-id="4c900-108">onEqualOp : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="4c900-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onnonequalop--unit--unit-ctl"></a><span data-ttu-id="4c900-109">onNonEqualOp : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="4c900-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="4c900-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c900-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

