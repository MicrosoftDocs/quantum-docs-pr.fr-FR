---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicC
title: Opération ApplyIfElseIntrinsicC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 178d4b704d84090f1f8592b857c3da659e5c50bb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708987"
---
# <a name="applyifelseintrinsicc-operation"></a><span data-ttu-id="10e96-102">Opération ApplyIfElseIntrinsicC</span><span class="sxs-lookup"><span data-stu-id="10e96-102">ApplyIfElseIntrinsicC operation</span></span>

<span data-ttu-id="10e96-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="10e96-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="10e96-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10e96-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseIntrinsicC (measurementResult : Result, onResultZeroOp : (Unit => Unit is Ctl), onResultOneOp : (Unit => Unit is Ctl)) : Unit
```


## <a name="input"></a><span data-ttu-id="10e96-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="10e96-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="10e96-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="10e96-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit-ctl"></a><span data-ttu-id="10e96-107">onResultZeroOp : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="10e96-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onresultoneop--unit--unit-ctl"></a><span data-ttu-id="10e96-108">onResultOneOp : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="10e96-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="10e96-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10e96-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

