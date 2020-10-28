---
uid: Microsoft.Quantum.Canon.DelayA
title: Opération retardée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 77c40633824ccd9250252804b08d7400936515dd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704243"
---
# <a name="delaya-operation"></a><span data-ttu-id="0358a-102">Opération retardée</span><span class="sxs-lookup"><span data-stu-id="0358a-102">DelayA operation</span></span>

<span data-ttu-id="0358a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0358a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0358a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0358a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0358a-105">Applique une opération donnée avec un délai.</span><span class="sxs-lookup"><span data-stu-id="0358a-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="0358a-106">Description</span><span class="sxs-lookup"><span data-stu-id="0358a-106">Description</span></span>

<span data-ttu-id="0358a-107">Pour une opération donnée et une entrée à cette opération, applique l’opération une fois qu’une entrée supplémentaire est fournie.</span><span class="sxs-lookup"><span data-stu-id="0358a-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="0358a-108">En particulier, l’expression `Delay(op, arg, _)` est une opération qui s’applique `op` à lorsqu’elle est `arg` appelée.</span><span class="sxs-lookup"><span data-stu-id="0358a-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="0358a-109">`Delay(op,arg,_)`L’expression permet de retarder l’application de `op` .</span><span class="sxs-lookup"><span data-stu-id="0358a-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="0358a-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="0358a-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="0358a-111">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0358a-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0358a-112">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="0358a-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="0358a-113">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="0358a-113">arg : 'T</span></span>

<span data-ttu-id="0358a-114">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="0358a-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="0358a-115">aux : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0358a-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="0358a-116">Argument utilisé pour retarder l’application de l’opération à l’aide d’une application partielle.</span><span class="sxs-lookup"><span data-stu-id="0358a-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0358a-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0358a-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0358a-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0358a-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0358a-119">Peut</span><span class="sxs-lookup"><span data-stu-id="0358a-119">'T</span></span>

<span data-ttu-id="0358a-120">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="0358a-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="0358a-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0358a-121">See Also</span></span>

- [<span data-ttu-id="0358a-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="0358a-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="0358a-123">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="0358a-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)