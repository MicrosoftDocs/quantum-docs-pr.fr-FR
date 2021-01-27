---
uid: Microsoft.Quantum.Canon.DelayCA
title: Opération DelayCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: a8606cde976882bba0eb23467932b9ee0ed36696
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840616"
---
# <a name="delayca-operation"></a><span data-ttu-id="71a71-102">Opération DelayCA</span><span class="sxs-lookup"><span data-stu-id="71a71-102">DelayCA operation</span></span>

<span data-ttu-id="71a71-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71a71-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71a71-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71a71-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71a71-105">Applique une opération donnée avec un délai.</span><span class="sxs-lookup"><span data-stu-id="71a71-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="71a71-106">Description</span><span class="sxs-lookup"><span data-stu-id="71a71-106">Description</span></span>

<span data-ttu-id="71a71-107">Pour une opération donnée et une entrée à cette opération, applique l’opération une fois qu’une entrée supplémentaire est fournie.</span><span class="sxs-lookup"><span data-stu-id="71a71-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="71a71-108">En particulier, l’expression `Delay(op, arg, _)` est une opération qui s’applique `op` à lorsqu’elle est `arg` appelée.</span><span class="sxs-lookup"><span data-stu-id="71a71-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="71a71-109">`Delay(op,arg,_)`L’expression permet de retarder l’application de `op` .</span><span class="sxs-lookup"><span data-stu-id="71a71-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="71a71-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="71a71-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="71a71-111">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="71a71-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="71a71-112">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="71a71-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="71a71-113">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="71a71-113">arg : 'T</span></span>

<span data-ttu-id="71a71-114">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="71a71-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="71a71-115">aux : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71a71-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="71a71-116">Argument utilisé pour retarder l’application de l’opération à l’aide d’une application partielle.</span><span class="sxs-lookup"><span data-stu-id="71a71-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71a71-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71a71-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="71a71-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="71a71-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71a71-119">Peut</span><span class="sxs-lookup"><span data-stu-id="71a71-119">'T</span></span>

<span data-ttu-id="71a71-120">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="71a71-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="71a71-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71a71-121">See Also</span></span>

- [<span data-ttu-id="71a71-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="71a71-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="71a71-123">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="71a71-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)