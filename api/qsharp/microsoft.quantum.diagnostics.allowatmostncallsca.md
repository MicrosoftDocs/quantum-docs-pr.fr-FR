---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Opération AllowAtMostNCallsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702793"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="110a8-102">Opération AllowAtMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="110a8-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="110a8-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="110a8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="110a8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="110a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="110a8-105">Entre un appel à cette opération et son voisin, déclare qu’une opération donnée est appelée au plus un certain nombre de fois.</span><span class="sxs-lookup"><span data-stu-id="110a8-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="110a8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="110a8-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="110a8-107">nTimes : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="110a8-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="110a8-108">Nombre maximal de fois où `op` peut être appelé.</span><span class="sxs-lookup"><span data-stu-id="110a8-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="110a8-109">OP : 'TInput => 'TOutput Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="110a8-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="110a8-110">Opération dont les appels doivent être restreints.</span><span class="sxs-lookup"><span data-stu-id="110a8-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="110a8-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="110a8-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="110a8-112">Message à afficher en cas d’échec.</span><span class="sxs-lookup"><span data-stu-id="110a8-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="110a8-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="110a8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="110a8-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="110a8-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="110a8-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="110a8-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="110a8-116">«TOutput</span><span class="sxs-lookup"><span data-stu-id="110a8-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="110a8-117">Notes</span><span class="sxs-lookup"><span data-stu-id="110a8-117">Remarks</span></span>

<span data-ttu-id="110a8-118">Cette opération peut être remplacée par une absence d’opération sur les cibles qui ne la prennent pas en charge.</span><span class="sxs-lookup"><span data-stu-id="110a8-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>