---
uid: Microsoft.Quantum.Canon.DelayC
title: Opération DelayC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216487"
---
# <a name="delayc-operation"></a><span data-ttu-id="5e470-102">Opération DelayC</span><span class="sxs-lookup"><span data-stu-id="5e470-102">DelayC operation</span></span>

<span data-ttu-id="5e470-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5e470-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5e470-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e470-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e470-105">Applique une opération donnée avec un délai.</span><span class="sxs-lookup"><span data-stu-id="5e470-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="5e470-106">Description</span><span class="sxs-lookup"><span data-stu-id="5e470-106">Description</span></span>

<span data-ttu-id="5e470-107">Pour une opération donnée et une entrée à cette opération, applique l’opération une fois qu’une entrée supplémentaire est fournie.</span><span class="sxs-lookup"><span data-stu-id="5e470-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="5e470-108">En particulier, l’expression `Delay(op, arg, _)` est une opération qui s’applique `op` à lorsqu’elle est `arg` appelée.</span><span class="sxs-lookup"><span data-stu-id="5e470-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="5e470-109">`Delay(op,arg,_)`L’expression permet de retarder l’application de `op` .</span><span class="sxs-lookup"><span data-stu-id="5e470-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="5e470-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="5e470-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="5e470-111">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="5e470-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="5e470-112">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="5e470-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="5e470-113">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="5e470-113">arg : 'T</span></span>

<span data-ttu-id="5e470-114">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="5e470-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="5e470-115">aux : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e470-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="5e470-116">Argument utilisé pour retarder l’application de l’opération à l’aide d’une application partielle.</span><span class="sxs-lookup"><span data-stu-id="5e470-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e470-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e470-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5e470-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="5e470-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5e470-119">Peut</span><span class="sxs-lookup"><span data-stu-id="5e470-119">'T</span></span>

<span data-ttu-id="5e470-120">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="5e470-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e470-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e470-121">See Also</span></span>

- [<span data-ttu-id="5e470-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="5e470-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="5e470-123">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="5e470-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)