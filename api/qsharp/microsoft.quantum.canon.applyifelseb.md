---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: Opération ApplyIfElseB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 68c06a5141b9ff423c2d18adc3a9e162eed939f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705342"
---
# <a name="applyifelseb-operation"></a><span data-ttu-id="10e0d-102">Opération ApplyIfElseB</span><span class="sxs-lookup"><span data-stu-id="10e0d-102">ApplyIfElseB operation</span></span>

<span data-ttu-id="10e0d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="10e0d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="10e0d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10e0d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10e0d-105">Applique l’une des deux opérations, en fonction de la valeur d’un bit classique.</span><span class="sxs-lookup"><span data-stu-id="10e0d-105">Applies one of two operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="10e0d-106">Description</span><span class="sxs-lookup"><span data-stu-id="10e0d-106">Description</span></span>

<span data-ttu-id="10e0d-107">À partir d’un bit `bit` , applique l’opération `trueOp` avec `trueInput` comme entrée lorsque `bit` est `true` et s’applique `falseOp(falseInput)` lorsque `bit` est `false` .</span><span class="sxs-lookup"><span data-stu-id="10e0d-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="10e0d-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="10e0d-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="10e0d-109">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="10e0d-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="10e0d-110">Valeur booléenne utilisée pour déterminer si `trueOp` ou `falseOp` est appliqué.</span><span class="sxs-lookup"><span data-stu-id="10e0d-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit"></a><span data-ttu-id="10e0d-111">trueOp : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10e0d-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="10e0d-112">Opération à appliquer lorsque a la `bit` valeur `true` .</span><span class="sxs-lookup"><span data-stu-id="10e0d-112">The operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="10e0d-113">trueInput : 't</span><span class="sxs-lookup"><span data-stu-id="10e0d-113">trueInput : 'T</span></span>

<span data-ttu-id="10e0d-114">Entrée à fournir `trueOp` lorsque a la valeur `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="10e0d-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit"></a><span data-ttu-id="10e0d-115">falseOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10e0d-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="10e0d-116">Opération à appliquer lorsque a la `bit` valeur `false` .</span><span class="sxs-lookup"><span data-stu-id="10e0d-116">The operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="10e0d-117">falseInput : 'U</span><span class="sxs-lookup"><span data-stu-id="10e0d-117">falseInput : 'U</span></span>

<span data-ttu-id="10e0d-118">Entrée à fournir `falseOp` lorsque a la valeur `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="10e0d-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="10e0d-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10e0d-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="10e0d-120">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="10e0d-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="10e0d-121">Peut</span><span class="sxs-lookup"><span data-stu-id="10e0d-121">'T</span></span>

<span data-ttu-id="10e0d-122">Type d’entrée de l’opération `trueOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="10e0d-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="10e0d-123">'U</span><span class="sxs-lookup"><span data-stu-id="10e0d-123">'U</span></span>

<span data-ttu-id="10e0d-124">Type d’entrée de l’opération `falseOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="10e0d-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="10e0d-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10e0d-125">See Also</span></span>

- [<span data-ttu-id="10e0d-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="10e0d-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="10e0d-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="10e0d-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="10e0d-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="10e0d-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="10e0d-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="10e0d-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="10e0d-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="10e0d-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)