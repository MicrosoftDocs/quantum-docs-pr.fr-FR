---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: Opération ApplyIfElseRA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: 48819440bf0d55f9a44ca8f76927692d48925e50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192704"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="c393a-102">Opération ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="c393a-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="c393a-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="c393a-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="c393a-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c393a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="c393a-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="c393a-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="c393a-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="c393a-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="c393a-107">onResultZeroOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="c393a-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="c393a-108">zeroArg : 't</span><span class="sxs-lookup"><span data-stu-id="c393a-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-adj"></a><span data-ttu-id="c393a-109">onResultOneOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="c393a-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--u"></a><span data-ttu-id="c393a-110">oneArg : 'U</span><span class="sxs-lookup"><span data-stu-id="c393a-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="c393a-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c393a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c393a-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c393a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c393a-113">Peut</span><span class="sxs-lookup"><span data-stu-id="c393a-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="c393a-114">'U</span><span class="sxs-lookup"><span data-stu-id="c393a-114">'U</span></span>
