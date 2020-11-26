---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Opération ApplyToElementC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217575"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="479be-102">Opération ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="479be-102">ApplyToElementC operation</span></span>

<span data-ttu-id="479be-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="479be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="479be-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="479be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="479be-105">Applique une opération à un élément donné d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="479be-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="479be-106">Description</span><span class="sxs-lookup"><span data-stu-id="479be-106">Description</span></span>

<span data-ttu-id="479be-107">À partir d’une opération `op` , d’un index `index` et d’un tableau de cibles `targets` , s’applique `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="479be-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="479be-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="479be-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="479be-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="479be-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="479be-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="479be-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="479be-111">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="479be-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="479be-112">Index dans le tableau de cibles.</span><span class="sxs-lookup"><span data-stu-id="479be-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="479be-113">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="479be-113">targets : 'T[]</span></span>

<span data-ttu-id="479be-114">Tableau de cibles possibles pour `op` .</span><span class="sxs-lookup"><span data-stu-id="479be-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="479be-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="479be-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="479be-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="479be-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="479be-117">Peut</span><span class="sxs-lookup"><span data-stu-id="479be-117">'T</span></span>

<span data-ttu-id="479be-118">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="479be-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="479be-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="479be-119">See Also</span></span>

- [<span data-ttu-id="479be-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="479be-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="479be-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="479be-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="479be-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="479be-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)