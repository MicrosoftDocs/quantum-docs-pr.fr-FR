---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: Opération ApplyIfZeroA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: 124c5bbabc9e22804734ddbde955312db9655187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709380"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="6f9ef-102">Opération ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="6f9ef-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="6f9ef-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="6f9ef-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="6f9ef-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f9ef-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="6f9ef-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="6f9ef-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="6f9ef-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="6f9ef-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-adj"></a><span data-ttu-id="6f9ef-107">onResultZeroOp : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f9ef-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="6f9ef-108">zeroArg : 't</span><span class="sxs-lookup"><span data-stu-id="6f9ef-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="6f9ef-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f9ef-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6f9ef-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6f9ef-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6f9ef-111">Peut</span><span class="sxs-lookup"><span data-stu-id="6f9ef-111">'T</span></span>
