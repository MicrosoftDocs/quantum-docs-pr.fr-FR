---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: Opération ApplyIfElseR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 78c1cf23614fbb7c27122548de487c7350467948
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705307"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="d4141-102">Opération ApplyIfElseR</span><span class="sxs-lookup"><span data-stu-id="d4141-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="d4141-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d4141-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d4141-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4141-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4141-105">Applique l’une des deux opérations, en fonction de la valeur d’un résultat classique.</span><span class="sxs-lookup"><span data-stu-id="d4141-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="d4141-106">Description</span><span class="sxs-lookup"><span data-stu-id="d4141-106">Description</span></span>

<span data-ttu-id="d4141-107">Avec un résultat donné `result` , applique l’opération `zeroOp` avec `zeroInput` comme entrée lorsque `result` est égal à `Zero` et s’applique `oneOp(oneInput)` quand `result == One` .</span><span class="sxs-lookup"><span data-stu-id="d4141-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="d4141-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="d4141-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="d4141-109">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="d4141-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="d4141-110">Résultat de mesure utilisé pour déterminer si `zeroOp` ou `oneOp` est appliqué.</span><span class="sxs-lookup"><span data-stu-id="d4141-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="d4141-111">zeroOp : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4141-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d4141-112">Opération à appliquer lorsque `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="d4141-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="d4141-113">zeroInput : 't</span><span class="sxs-lookup"><span data-stu-id="d4141-113">zeroInput : 'T</span></span>

<span data-ttu-id="d4141-114">Entrée à fournir `zeroOp` lorsque `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="d4141-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="d4141-115">oneOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4141-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d4141-116">Opération à appliquer lorsque `result == One` .</span><span class="sxs-lookup"><span data-stu-id="d4141-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="d4141-117">oneInput : 'U</span><span class="sxs-lookup"><span data-stu-id="d4141-117">oneInput : 'U</span></span>

<span data-ttu-id="d4141-118">Entrée à fournir `oneOp` lorsque `result == One` .</span><span class="sxs-lookup"><span data-stu-id="d4141-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4141-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4141-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d4141-120">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d4141-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d4141-121">Peut</span><span class="sxs-lookup"><span data-stu-id="d4141-121">'T</span></span>

<span data-ttu-id="d4141-122">Type d’entrée de l’opération `zeroOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="d4141-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="d4141-123">'U</span><span class="sxs-lookup"><span data-stu-id="d4141-123">'U</span></span>

<span data-ttu-id="d4141-124">Type d’entrée de l’opération `oneOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="d4141-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4141-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4141-125">See Also</span></span>

- [<span data-ttu-id="d4141-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="d4141-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="d4141-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="d4141-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="d4141-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="d4141-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="d4141-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="d4141-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="d4141-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="d4141-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)