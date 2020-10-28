---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: Opération ApplyIfElseBC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 032d92484dc96481cb981d9d8acfeed248a9116d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705339"
---
# <a name="applyifelsebc-operation"></a><span data-ttu-id="c5801-102">Opération ApplyIfElseBC</span><span class="sxs-lookup"><span data-stu-id="c5801-102">ApplyIfElseBC operation</span></span>

<span data-ttu-id="c5801-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c5801-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c5801-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5801-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5801-105">Applique l’une des deux opérations contrôlable, en fonction de la valeur d’un bit classique.</span><span class="sxs-lookup"><span data-stu-id="c5801-105">Applies one of two controllable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="c5801-106">Description</span><span class="sxs-lookup"><span data-stu-id="c5801-106">Description</span></span>

<span data-ttu-id="c5801-107">À partir d’un bit `bit` , applique l’opération `trueOp` avec `trueInput` comme entrée lorsque `bit` est `true` et s’applique `falseOp(falseInput)` lorsque `bit` est `false` .</span><span class="sxs-lookup"><span data-stu-id="c5801-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="c5801-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="c5801-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="c5801-109">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5801-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5801-110">Valeur booléenne utilisée pour déterminer si `trueOp` ou `falseOp` est appliqué.</span><span class="sxs-lookup"><span data-stu-id="c5801-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-ctl"></a><span data-ttu-id="c5801-111">trueOp : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5801-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c5801-112">Opération contrôlable à appliquer lorsque `bit` a la valeur `true` .</span><span class="sxs-lookup"><span data-stu-id="c5801-112">The controllable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="c5801-113">trueInput : 't</span><span class="sxs-lookup"><span data-stu-id="c5801-113">trueInput : 'T</span></span>

<span data-ttu-id="c5801-114">Entrée à fournir `trueOp` lorsque a la valeur `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="c5801-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-ctl"></a><span data-ttu-id="c5801-115">falseOp : 'U => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5801-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c5801-116">Opération contrôlable à appliquer lorsque `bit` a la valeur `false` .</span><span class="sxs-lookup"><span data-stu-id="c5801-116">The controllable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="c5801-117">falseInput : 'U</span><span class="sxs-lookup"><span data-stu-id="c5801-117">falseInput : 'U</span></span>

<span data-ttu-id="c5801-118">Entrée à fournir `falseOp` lorsque a la valeur `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="c5801-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5801-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5801-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c5801-120">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c5801-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5801-121">Peut</span><span class="sxs-lookup"><span data-stu-id="c5801-121">'T</span></span>

<span data-ttu-id="c5801-122">Type d’entrée de l’opération `trueOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="c5801-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="c5801-123">'U</span><span class="sxs-lookup"><span data-stu-id="c5801-123">'U</span></span>

<span data-ttu-id="c5801-124">Type d’entrée de l’opération `falseOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="c5801-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5801-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c5801-125">See Also</span></span>

- [<span data-ttu-id="c5801-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="c5801-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="c5801-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="c5801-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="c5801-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="c5801-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="c5801-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="c5801-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="c5801-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="c5801-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)