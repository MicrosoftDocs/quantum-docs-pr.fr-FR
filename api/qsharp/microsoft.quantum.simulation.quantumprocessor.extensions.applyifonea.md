---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: Opération ApplyIfOneA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: c18133403a545f7dc7b9f213a42ed09cd194f2d7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709248"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="89283-102">Opération ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="89283-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="89283-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="89283-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="89283-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89283-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="89283-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="89283-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="89283-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="89283-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-adj"></a><span data-ttu-id="89283-107">onResultOneOp : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89283-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="89283-108">oneArg : 't</span><span class="sxs-lookup"><span data-stu-id="89283-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="89283-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89283-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="89283-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="89283-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="89283-111">Peut</span><span class="sxs-lookup"><span data-stu-id="89283-111">'T</span></span>

