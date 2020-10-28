---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: Opération ApplyIfZero
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: a76c6269ac4445326ac357fe2cdd552847089a6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708087"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="56854-102">Opération ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="56854-102">ApplyIfZero operation</span></span>

<span data-ttu-id="56854-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="56854-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="56854-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56854-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="56854-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="56854-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="56854-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="56854-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="56854-107">onResultZeroOp : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56854-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="56854-108">zeroArg : 't</span><span class="sxs-lookup"><span data-stu-id="56854-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="56854-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56854-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="56854-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="56854-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56854-111">Peut</span><span class="sxs-lookup"><span data-stu-id="56854-111">'T</span></span>

