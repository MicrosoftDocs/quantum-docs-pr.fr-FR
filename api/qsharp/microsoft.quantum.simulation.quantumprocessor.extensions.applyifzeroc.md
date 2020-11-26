---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: Opération ApplyIfZeroC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 9a73ea9ec607bec89c996c096b235a72185b453d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230835"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="0b69e-102">Opération ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="0b69e-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="0b69e-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="0b69e-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="0b69e-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0b69e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="0b69e-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="0b69e-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="0b69e-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="0b69e-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="0b69e-107">onResultZeroOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="0b69e-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="0b69e-108">zeroArg : 't</span><span class="sxs-lookup"><span data-stu-id="0b69e-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="0b69e-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b69e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0b69e-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0b69e-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b69e-111">Peut</span><span class="sxs-lookup"><span data-stu-id="0b69e-111">'T</span></span>

