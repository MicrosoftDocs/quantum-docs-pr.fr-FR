---
uid: Microsoft.Quantum.Canon.DelayA
title: Opération retardée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c7385cfcdf782347feb8d95311205a9311f4c929
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840666"
---
# <a name="delaya-operation"></a><span data-ttu-id="3c83c-102">Opération retardée</span><span class="sxs-lookup"><span data-stu-id="3c83c-102">DelayA operation</span></span>

<span data-ttu-id="3c83c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c83c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c83c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c83c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c83c-105">Applique une opération donnée avec un délai.</span><span class="sxs-lookup"><span data-stu-id="3c83c-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="3c83c-106">Description</span><span class="sxs-lookup"><span data-stu-id="3c83c-106">Description</span></span>

<span data-ttu-id="3c83c-107">Pour une opération donnée et une entrée à cette opération, applique l’opération une fois qu’une entrée supplémentaire est fournie.</span><span class="sxs-lookup"><span data-stu-id="3c83c-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="3c83c-108">En particulier, l’expression `Delay(op, arg, _)` est une opération qui s’applique `op` à lorsqu’elle est `arg` appelée.</span><span class="sxs-lookup"><span data-stu-id="3c83c-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="3c83c-109">`Delay(op,arg,_)`L’expression permet de retarder l’application de `op` .</span><span class="sxs-lookup"><span data-stu-id="3c83c-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="3c83c-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="3c83c-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="3c83c-111">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="3c83c-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3c83c-112">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="3c83c-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="3c83c-113">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="3c83c-113">arg : 'T</span></span>

<span data-ttu-id="3c83c-114">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="3c83c-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="3c83c-115">aux : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c83c-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="3c83c-116">Argument utilisé pour retarder l’application de l’opération à l’aide d’une application partielle.</span><span class="sxs-lookup"><span data-stu-id="3c83c-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c83c-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c83c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3c83c-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="3c83c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c83c-119">Peut</span><span class="sxs-lookup"><span data-stu-id="3c83c-119">'T</span></span>

<span data-ttu-id="3c83c-120">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="3c83c-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c83c-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c83c-121">See Also</span></span>

- [<span data-ttu-id="3c83c-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="3c83c-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="3c83c-123">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="3c83c-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)