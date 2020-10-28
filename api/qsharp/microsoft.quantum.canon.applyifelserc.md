---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: Opération ApplyIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: 45bd0f46fb2e28c5c9aaa21cb7ec065baf279d2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705283"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="172f9-102">Opération ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="172f9-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="172f9-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="172f9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="172f9-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="172f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="172f9-105">Applique l’une des deux opérations contrôlable, en fonction de la valeur d’un résultat classique.</span><span class="sxs-lookup"><span data-stu-id="172f9-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="172f9-106">Description</span><span class="sxs-lookup"><span data-stu-id="172f9-106">Description</span></span>

<span data-ttu-id="172f9-107">Avec un résultat donné `result` , applique l’opération `zeroOp` avec `zeroInput` comme entrée lorsque `result` est égal à `Zero` et s’applique `oneOp(oneInput)` quand `result == One` .</span><span class="sxs-lookup"><span data-stu-id="172f9-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="172f9-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="172f9-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="172f9-109">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="172f9-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="172f9-110">Résultat de mesure utilisé pour déterminer si `zeroOp` ou `oneOp` est appliqué.</span><span class="sxs-lookup"><span data-stu-id="172f9-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-ctl"></a><span data-ttu-id="172f9-111">zeroOp : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="172f9-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="172f9-112">Opération contrôlable à appliquer lorsque `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="172f9-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="172f9-113">zeroInput : 't</span><span class="sxs-lookup"><span data-stu-id="172f9-113">zeroInput : 'T</span></span>

<span data-ttu-id="172f9-114">Entrée à fournir `zeroOp` lorsque `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="172f9-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-ctl"></a><span data-ttu-id="172f9-115">oneOp : 'U => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="172f9-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="172f9-116">Opération contrôlable à appliquer lorsque `result == One` .</span><span class="sxs-lookup"><span data-stu-id="172f9-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="172f9-117">oneInput : 'U</span><span class="sxs-lookup"><span data-stu-id="172f9-117">oneInput : 'U</span></span>

<span data-ttu-id="172f9-118">Entrée à fournir `oneOp` lorsque `result == One` .</span><span class="sxs-lookup"><span data-stu-id="172f9-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="172f9-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="172f9-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="172f9-120">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="172f9-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="172f9-121">Peut</span><span class="sxs-lookup"><span data-stu-id="172f9-121">'T</span></span>

<span data-ttu-id="172f9-122">Type d’entrée de l’opération `zeroOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="172f9-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="172f9-123">'U</span><span class="sxs-lookup"><span data-stu-id="172f9-123">'U</span></span>

<span data-ttu-id="172f9-124">Type d’entrée de l’opération `oneOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="172f9-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="172f9-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="172f9-125">See Also</span></span>

- [<span data-ttu-id="172f9-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="172f9-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="172f9-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="172f9-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="172f9-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="172f9-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="172f9-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="172f9-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="172f9-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="172f9-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)