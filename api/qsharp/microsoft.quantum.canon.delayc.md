---
uid: Microsoft.Quantum.Canon.DelayC
title: Opération DelayC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: acb817c3322063353dc08c5d6f8c539391b3bf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704238"
---
# <a name="delayc-operation"></a><span data-ttu-id="bad0c-102">Opération DelayC</span><span class="sxs-lookup"><span data-stu-id="bad0c-102">DelayC operation</span></span>

<span data-ttu-id="bad0c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bad0c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bad0c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bad0c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bad0c-105">Applique une opération donnée avec un délai.</span><span class="sxs-lookup"><span data-stu-id="bad0c-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="bad0c-106">Description</span><span class="sxs-lookup"><span data-stu-id="bad0c-106">Description</span></span>

<span data-ttu-id="bad0c-107">Pour une opération donnée et une entrée à cette opération, applique l’opération une fois qu’une entrée supplémentaire est fournie.</span><span class="sxs-lookup"><span data-stu-id="bad0c-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="bad0c-108">En particulier, l’expression `Delay(op, arg, _)` est une opération qui s’applique `op` à lorsqu’elle est `arg` appelée.</span><span class="sxs-lookup"><span data-stu-id="bad0c-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="bad0c-109">`Delay(op,arg,_)`L’expression permet de retarder l’application de `op` .</span><span class="sxs-lookup"><span data-stu-id="bad0c-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="bad0c-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="bad0c-110">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="bad0c-111">OP : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bad0c-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="bad0c-112">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="bad0c-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="bad0c-113">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="bad0c-113">arg : 'T</span></span>

<span data-ttu-id="bad0c-114">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="bad0c-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="bad0c-115">aux : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bad0c-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="bad0c-116">Argument utilisé pour retarder l’application de l’opération à l’aide d’une application partielle.</span><span class="sxs-lookup"><span data-stu-id="bad0c-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bad0c-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bad0c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bad0c-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="bad0c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bad0c-119">Peut</span><span class="sxs-lookup"><span data-stu-id="bad0c-119">'T</span></span>

<span data-ttu-id="bad0c-120">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="bad0c-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="bad0c-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bad0c-121">See Also</span></span>

- [<span data-ttu-id="bad0c-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="bad0c-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="bad0c-123">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="bad0c-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)