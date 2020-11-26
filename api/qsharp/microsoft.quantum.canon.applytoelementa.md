---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Opération ApplyToElementA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: e8318a7873476ee49d8e1e235e6c917a38ee6200
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208871"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="afe38-102">Opération ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="afe38-102">ApplyToElementA operation</span></span>

<span data-ttu-id="afe38-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="afe38-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="afe38-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="afe38-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="afe38-105">Applique une opération à un élément donné d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="afe38-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="afe38-106">Description</span><span class="sxs-lookup"><span data-stu-id="afe38-106">Description</span></span>

<span data-ttu-id="afe38-107">À partir d’une opération `op` , d’un index `index` et d’un tableau de cibles `targets` , s’applique `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="afe38-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="afe38-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="afe38-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="afe38-109">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="afe38-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="afe38-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="afe38-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="afe38-111">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="afe38-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="afe38-112">Index dans le tableau de cibles.</span><span class="sxs-lookup"><span data-stu-id="afe38-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="afe38-113">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="afe38-113">targets : 'T[]</span></span>

<span data-ttu-id="afe38-114">Tableau de cibles possibles pour `op` .</span><span class="sxs-lookup"><span data-stu-id="afe38-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="afe38-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="afe38-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="afe38-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="afe38-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="afe38-117">Peut</span><span class="sxs-lookup"><span data-stu-id="afe38-117">'T</span></span>

<span data-ttu-id="afe38-118">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="afe38-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="afe38-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="afe38-119">See Also</span></span>

- [<span data-ttu-id="afe38-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="afe38-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="afe38-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="afe38-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="afe38-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="afe38-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)