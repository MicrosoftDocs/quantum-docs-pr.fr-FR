---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: Opération ApplyIfElseRA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 3ebd09b1e5876ff397f3524ba828ba26a271e91e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218595"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="9dd4a-102">Opération ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="9dd4a-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="9dd4a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9dd4a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9dd4a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9dd4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9dd4a-105">Applique l’une des deux opérations adjointable, en fonction de la valeur d’un résultat classique.</span><span class="sxs-lookup"><span data-stu-id="9dd4a-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="9dd4a-106">Description</span><span class="sxs-lookup"><span data-stu-id="9dd4a-106">Description</span></span>

<span data-ttu-id="9dd4a-107">Avec un résultat donné `result` , applique l’opération `zeroOp` avec `zeroInput` comme entrée lorsque `result` est égal à `Zero` et s’applique `oneOp(oneInput)` quand `result == One` .</span><span class="sxs-lookup"><span data-stu-id="9dd4a-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="9dd4a-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="9dd4a-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="9dd4a-109">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="9dd4a-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="9dd4a-110">Résultat de mesure utilisé pour déterminer si `zeroOp` ou `oneOp` est appliqué.</span><span class="sxs-lookup"><span data-stu-id="9dd4a-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj"></a><span data-ttu-id="9dd4a-111">zeroOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="9dd4a-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9dd4a-112">Opération adjointable à appliquer lorsque `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="9dd4a-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="9dd4a-113">zeroInput : 't</span><span class="sxs-lookup"><span data-stu-id="9dd4a-113">zeroInput : 'T</span></span>

<span data-ttu-id="9dd4a-114">Entrée à fournir `zeroOp` lorsque `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="9dd4a-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj"></a><span data-ttu-id="9dd4a-115">oneOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="9dd4a-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9dd4a-116">Opération adjointable à appliquer lorsque `result == One` .</span><span class="sxs-lookup"><span data-stu-id="9dd4a-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="9dd4a-117">oneInput : 'U</span><span class="sxs-lookup"><span data-stu-id="9dd4a-117">oneInput : 'U</span></span>

<span data-ttu-id="9dd4a-118">Entrée à fournir `oneOp` lorsque `result == One` .</span><span class="sxs-lookup"><span data-stu-id="9dd4a-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9dd4a-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9dd4a-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9dd4a-120">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9dd4a-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9dd4a-121">Peut</span><span class="sxs-lookup"><span data-stu-id="9dd4a-121">'T</span></span>

<span data-ttu-id="9dd4a-122">Type d’entrée de l’opération `zeroOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="9dd4a-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="9dd4a-123">'U</span><span class="sxs-lookup"><span data-stu-id="9dd4a-123">'U</span></span>

<span data-ttu-id="9dd4a-124">Type d’entrée de l’opération `oneOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="9dd4a-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9dd4a-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9dd4a-125">See Also</span></span>

- [<span data-ttu-id="9dd4a-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="9dd4a-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="9dd4a-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="9dd4a-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="9dd4a-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="9dd4a-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="9dd4a-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="9dd4a-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="9dd4a-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="9dd4a-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)