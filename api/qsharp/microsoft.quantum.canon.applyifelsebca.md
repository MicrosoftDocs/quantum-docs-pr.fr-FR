---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: Opération ApplyIfElseBCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: d36b16298ea177f16b7bbb260f069bfe35b9a72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218629"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="82701-102">Opération ApplyIfElseBCA</span><span class="sxs-lookup"><span data-stu-id="82701-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="82701-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="82701-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="82701-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="82701-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="82701-105">Applique l’une des deux opérations unitaires, en fonction de la valeur d’un bit classique.</span><span class="sxs-lookup"><span data-stu-id="82701-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="82701-106">Description</span><span class="sxs-lookup"><span data-stu-id="82701-106">Description</span></span>

<span data-ttu-id="82701-107">À partir d’un bit `bit` , applique l’opération `trueOp` avec `trueInput` comme entrée lorsque `bit` est `true` et s’applique `falseOp(falseInput)` lorsque `bit` est `false` .</span><span class="sxs-lookup"><span data-stu-id="82701-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="82701-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="82701-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="82701-109">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="82701-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82701-110">Valeur booléenne utilisée pour déterminer si `trueOp` ou `falseOp` est appliqué.</span><span class="sxs-lookup"><span data-stu-id="82701-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj--ctl"></a><span data-ttu-id="82701-111">trueOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="82701-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="82701-112">Opération unitaire à appliquer lorsque `bit` a la valeur `true` .</span><span class="sxs-lookup"><span data-stu-id="82701-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="82701-113">trueInput : 't</span><span class="sxs-lookup"><span data-stu-id="82701-113">trueInput : 'T</span></span>

<span data-ttu-id="82701-114">Entrée à fournir `trueOp` lorsque a la valeur `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="82701-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj--ctl"></a><span data-ttu-id="82701-115">falseOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="82701-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="82701-116">Opération unitaire à appliquer lorsque `bit` a la valeur `false` .</span><span class="sxs-lookup"><span data-stu-id="82701-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="82701-117">falseInput : 'U</span><span class="sxs-lookup"><span data-stu-id="82701-117">falseInput : 'U</span></span>

<span data-ttu-id="82701-118">Entrée à fournir `falseOp` lorsque a la valeur `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="82701-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82701-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82701-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="82701-120">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="82701-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="82701-121">Peut</span><span class="sxs-lookup"><span data-stu-id="82701-121">'T</span></span>

<span data-ttu-id="82701-122">Type d’entrée de l’opération `trueOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="82701-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="82701-123">'U</span><span class="sxs-lookup"><span data-stu-id="82701-123">'U</span></span>

<span data-ttu-id="82701-124">Type d’entrée de l’opération `falseOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="82701-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="82701-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82701-125">See Also</span></span>

- [<span data-ttu-id="82701-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="82701-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="82701-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="82701-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="82701-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="82701-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="82701-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="82701-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="82701-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="82701-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)