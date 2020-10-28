---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: Opération ApplyToElementCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704899"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="76b54-102">Opération ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="76b54-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="76b54-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76b54-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76b54-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76b54-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76b54-105">Applique une opération à un élément donné d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="76b54-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="76b54-106">Description</span><span class="sxs-lookup"><span data-stu-id="76b54-106">Description</span></span>

<span data-ttu-id="76b54-107">À partir d’une opération `op` , d’un index `index` et d’un tableau de cibles `targets` , s’applique `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="76b54-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="76b54-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="76b54-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="76b54-109">OP : t [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="76b54-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="76b54-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="76b54-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="76b54-111">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76b54-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="76b54-112">Index dans le tableau de cibles.</span><span class="sxs-lookup"><span data-stu-id="76b54-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="76b54-113">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="76b54-113">targets : 'T[]</span></span>

<span data-ttu-id="76b54-114">Tableau de cibles possibles pour `op` .</span><span class="sxs-lookup"><span data-stu-id="76b54-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76b54-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76b54-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="76b54-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="76b54-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76b54-117">Peut</span><span class="sxs-lookup"><span data-stu-id="76b54-117">'T</span></span>

<span data-ttu-id="76b54-118">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="76b54-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="76b54-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76b54-119">See Also</span></span>

- [<span data-ttu-id="76b54-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="76b54-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="76b54-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="76b54-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="76b54-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="76b54-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)