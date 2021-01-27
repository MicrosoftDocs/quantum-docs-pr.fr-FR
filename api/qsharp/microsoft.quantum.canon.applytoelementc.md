---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Opération ApplyToElementC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850742"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="7ea07-102">Opération ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="7ea07-102">ApplyToElementC operation</span></span>

<span data-ttu-id="7ea07-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7ea07-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7ea07-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ea07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ea07-105">Applique une opération à un élément donné d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="7ea07-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="7ea07-106">Description</span><span class="sxs-lookup"><span data-stu-id="7ea07-106">Description</span></span>

<span data-ttu-id="7ea07-107">À partir d’une opération `op` , d’un index `index` et d’un tableau de cibles `targets` , s’applique `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="7ea07-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="7ea07-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="7ea07-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="7ea07-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="7ea07-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7ea07-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="7ea07-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="7ea07-111">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7ea07-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7ea07-112">Index dans le tableau de cibles.</span><span class="sxs-lookup"><span data-stu-id="7ea07-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="7ea07-113">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="7ea07-113">targets : 'T[]</span></span>

<span data-ttu-id="7ea07-114">Tableau de cibles possibles pour `op` .</span><span class="sxs-lookup"><span data-stu-id="7ea07-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7ea07-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ea07-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7ea07-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7ea07-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7ea07-117">Peut</span><span class="sxs-lookup"><span data-stu-id="7ea07-117">'T</span></span>

<span data-ttu-id="7ea07-118">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="7ea07-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ea07-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7ea07-119">See Also</span></span>

- [<span data-ttu-id="7ea07-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="7ea07-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="7ea07-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="7ea07-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="7ea07-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="7ea07-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)