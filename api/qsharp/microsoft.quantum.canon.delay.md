---
uid: Microsoft.Quantum.Canon.Delay
title: Opération de retardement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4f45527faa49f79fccff3892e928fed09f9f0bc8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216504"
---
# <a name="delay-operation"></a><span data-ttu-id="a1693-102">Opération de retardement</span><span class="sxs-lookup"><span data-stu-id="a1693-102">Delay operation</span></span>

<span data-ttu-id="a1693-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a1693-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a1693-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1693-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1693-105">Applique une opération donnée avec un délai.</span><span class="sxs-lookup"><span data-stu-id="a1693-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="a1693-106">Description</span><span class="sxs-lookup"><span data-stu-id="a1693-106">Description</span></span>

<span data-ttu-id="a1693-107">Pour une opération donnée et une entrée à cette opération, applique l’opération une fois qu’une entrée supplémentaire est fournie.</span><span class="sxs-lookup"><span data-stu-id="a1693-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="a1693-108">En particulier, l’expression `Delay(op, arg, _)` est une opération qui s’applique `op` à lorsqu’elle est `arg` appelée.</span><span class="sxs-lookup"><span data-stu-id="a1693-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="a1693-109">`Delay(op,arg,_)`L’expression permet de retarder l’application de `op` .</span><span class="sxs-lookup"><span data-stu-id="a1693-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="a1693-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="a1693-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="a1693-111">OP : 't => 'U</span><span class="sxs-lookup"><span data-stu-id="a1693-111">op : 'T => 'U</span></span> 

<span data-ttu-id="a1693-112">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="a1693-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="a1693-113">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="a1693-113">arg : 'T</span></span>

<span data-ttu-id="a1693-114">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="a1693-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="a1693-115">aux : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1693-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="a1693-116">Argument utilisé pour retarder l’application de l’opération à l’aide d’une application partielle.</span><span class="sxs-lookup"><span data-stu-id="a1693-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="a1693-117">Sortie : 'U</span><span class="sxs-lookup"><span data-stu-id="a1693-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a1693-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a1693-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a1693-119">Peut</span><span class="sxs-lookup"><span data-stu-id="a1693-119">'T</span></span>

<span data-ttu-id="a1693-120">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="a1693-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="a1693-121">'U</span><span class="sxs-lookup"><span data-stu-id="a1693-121">'U</span></span>

<span data-ttu-id="a1693-122">Type de retour de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="a1693-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1693-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1693-123">See Also</span></span>

- [<span data-ttu-id="a1693-124">Microsoft. Quantum. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="a1693-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="a1693-125">Microsoft. Quantum. Canon. retarder</span><span class="sxs-lookup"><span data-stu-id="a1693-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="a1693-126">Microsoft. Quantum. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="a1693-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="a1693-127">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="a1693-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)