---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Opération ApplyBlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852828"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="71684-102">Opération ApplyBlockEncodingByLCU</span><span class="sxs-lookup"><span data-stu-id="71684-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="71684-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="71684-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="71684-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71684-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71684-105">Implémentation de `BlockEncodingByLCU`.</span><span class="sxs-lookup"><span data-stu-id="71684-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="71684-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="71684-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="71684-107">statePreparation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="71684-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="71684-108">sélecteur : ('t, s) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="71684-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="71684-109">auxiliaire : 't</span><span class="sxs-lookup"><span data-stu-id="71684-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="71684-110">système :</span><span class="sxs-lookup"><span data-stu-id="71684-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="71684-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71684-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="71684-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="71684-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71684-113">Peut</span><span class="sxs-lookup"><span data-stu-id="71684-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="71684-114">Examin</span><span class="sxs-lookup"><span data-stu-id="71684-114">'S</span></span>

