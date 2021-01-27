---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: Opération ApplyIfZeroA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: 812b7a830d963b4bb73c32ba1c136e506789e997
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854197"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="b3c95-102">Opération ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="b3c95-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="b3c95-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b3c95-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b3c95-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b3c95-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b3c95-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="b3c95-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="b3c95-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="b3c95-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="b3c95-107">onResultZeroOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="b3c95-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="b3c95-108">zeroArg : 't</span><span class="sxs-lookup"><span data-stu-id="b3c95-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="b3c95-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3c95-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b3c95-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b3c95-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b3c95-111">Peut</span><span class="sxs-lookup"><span data-stu-id="b3c95-111">'T</span></span>

