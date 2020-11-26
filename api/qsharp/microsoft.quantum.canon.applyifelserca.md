---
uid: Microsoft.Quantum.Canon.ApplyIfElseRCA
title: Opération ApplyIfElseRCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical result.
ms.openlocfilehash: dfd1c16a25a2da507024813a380386c8f4e49d30
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218748"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="9299c-102">Opération ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="9299c-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="9299c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9299c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9299c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9299c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9299c-105">Applique l’une des deux opérations unitaires, en fonction de la valeur d’un résultat classique.</span><span class="sxs-lookup"><span data-stu-id="9299c-105">Applies one of two unitary operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRCA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj + Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Adj + Ctl), oneInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9299c-106">Description</span><span class="sxs-lookup"><span data-stu-id="9299c-106">Description</span></span>

<span data-ttu-id="9299c-107">Avec un résultat donné `result` , applique l’opération `zeroOp` avec `zeroInput` comme entrée lorsque `result` est égal à `Zero` et s’applique `oneOp(oneInput)` quand `result == One` .</span><span class="sxs-lookup"><span data-stu-id="9299c-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="9299c-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="9299c-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="9299c-109">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="9299c-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="9299c-110">Résultat de mesure utilisé pour déterminer si `zeroOp` ou `oneOp` est appliqué.</span><span class="sxs-lookup"><span data-stu-id="9299c-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="9299c-111">zeroOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="9299c-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9299c-112">Opération unitaire à appliquer lorsque `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="9299c-112">The unitary operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="9299c-113">zeroInput : 't</span><span class="sxs-lookup"><span data-stu-id="9299c-113">zeroInput : 'T</span></span>

<span data-ttu-id="9299c-114">Entrée à fournir `zeroOp` lorsque `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="9299c-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj--ctl"></a><span data-ttu-id="9299c-115">oneOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="9299c-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9299c-116">Opération unitaire à appliquer lorsque `result == One` .</span><span class="sxs-lookup"><span data-stu-id="9299c-116">The unitary operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="9299c-117">oneInput : 'U</span><span class="sxs-lookup"><span data-stu-id="9299c-117">oneInput : 'U</span></span>

<span data-ttu-id="9299c-118">Entrée à fournir `oneOp` lorsque `result == One` .</span><span class="sxs-lookup"><span data-stu-id="9299c-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9299c-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9299c-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9299c-120">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9299c-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9299c-121">Peut</span><span class="sxs-lookup"><span data-stu-id="9299c-121">'T</span></span>

<span data-ttu-id="9299c-122">Type d’entrée de l’opération `zeroOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="9299c-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="9299c-123">'U</span><span class="sxs-lookup"><span data-stu-id="9299c-123">'U</span></span>

<span data-ttu-id="9299c-124">Type d’entrée de l’opération `oneOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="9299c-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9299c-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9299c-125">See Also</span></span>

- [<span data-ttu-id="9299c-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="9299c-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="9299c-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="9299c-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="9299c-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="9299c-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="9299c-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="9299c-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="9299c-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="9299c-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)