---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: Opération ApplyIfZero
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: f0c8cfc2292cf30ee3ab86c486e982347086453b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858278"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="49371-102">Opération ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="49371-102">ApplyIfZero operation</span></span>

<span data-ttu-id="49371-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="49371-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="49371-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="49371-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="49371-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="49371-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="49371-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="49371-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="49371-107">onResultZeroOp : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49371-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="49371-108">zeroArg : 't</span><span class="sxs-lookup"><span data-stu-id="49371-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="49371-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49371-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="49371-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="49371-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="49371-111">Peut</span><span class="sxs-lookup"><span data-stu-id="49371-111">'T</span></span>

