---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: Opération ApplyIfElseBCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705326"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="ea712-102">Opération ApplyIfElseBCA</span><span class="sxs-lookup"><span data-stu-id="ea712-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="ea712-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ea712-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ea712-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea712-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea712-105">Applique l’une des deux opérations unitaires, en fonction de la valeur d’un bit classique.</span><span class="sxs-lookup"><span data-stu-id="ea712-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="ea712-106">Description</span><span class="sxs-lookup"><span data-stu-id="ea712-106">Description</span></span>

<span data-ttu-id="ea712-107">À partir d’un bit `bit` , applique l’opération `trueOp` avec `trueInput` comme entrée lorsque `bit` est `true` et s’applique `falseOp(falseInput)` lorsque `bit` est `false` .</span><span class="sxs-lookup"><span data-stu-id="ea712-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="ea712-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="ea712-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="ea712-109">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ea712-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ea712-110">Valeur booléenne utilisée pour déterminer si `trueOp` ou `falseOp` est appliqué.</span><span class="sxs-lookup"><span data-stu-id="ea712-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-adj--ctl"></a><span data-ttu-id="ea712-111">trueOp : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="ea712-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ea712-112">Opération unitaire à appliquer lorsque `bit` a la valeur `true` .</span><span class="sxs-lookup"><span data-stu-id="ea712-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="ea712-113">trueInput : 't</span><span class="sxs-lookup"><span data-stu-id="ea712-113">trueInput : 'T</span></span>

<span data-ttu-id="ea712-114">Entrée à fournir `trueOp` lorsque a la valeur `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="ea712-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-adj--ctl"></a><span data-ttu-id="ea712-115">falseOp : 'U [=> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="ea712-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ea712-116">Opération unitaire à appliquer lorsque `bit` a la valeur `false` .</span><span class="sxs-lookup"><span data-stu-id="ea712-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="ea712-117">falseInput : 'U</span><span class="sxs-lookup"><span data-stu-id="ea712-117">falseInput : 'U</span></span>

<span data-ttu-id="ea712-118">Entrée à fournir `falseOp` lorsque a la valeur `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="ea712-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea712-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea712-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ea712-120">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ea712-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ea712-121">Peut</span><span class="sxs-lookup"><span data-stu-id="ea712-121">'T</span></span>

<span data-ttu-id="ea712-122">Type d’entrée de l’opération `trueOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="ea712-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="ea712-123">'U</span><span class="sxs-lookup"><span data-stu-id="ea712-123">'U</span></span>

<span data-ttu-id="ea712-124">Type d’entrée de l’opération `falseOp` à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="ea712-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea712-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea712-125">See Also</span></span>

- [<span data-ttu-id="ea712-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="ea712-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="ea712-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="ea712-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="ea712-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="ea712-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="ea712-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="ea712-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="ea712-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="ea712-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)