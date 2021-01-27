---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Opération ApplyToElementA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 57d870c7fbd099212b13f75bd85e57c046280d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850766"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="9990c-102">Opération ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="9990c-102">ApplyToElementA operation</span></span>

<span data-ttu-id="9990c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9990c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9990c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9990c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9990c-105">Applique une opération à un élément donné d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="9990c-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="9990c-106">Description</span><span class="sxs-lookup"><span data-stu-id="9990c-106">Description</span></span>

<span data-ttu-id="9990c-107">À partir d’une opération `op` , d’un index `index` et d’un tableau de cibles `targets` , s’applique `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="9990c-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="9990c-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="9990c-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="9990c-109">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="9990c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9990c-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="9990c-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="9990c-111">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9990c-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9990c-112">Index dans le tableau de cibles.</span><span class="sxs-lookup"><span data-stu-id="9990c-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9990c-113">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="9990c-113">targets : 'T[]</span></span>

<span data-ttu-id="9990c-114">Tableau de cibles possibles pour `op` .</span><span class="sxs-lookup"><span data-stu-id="9990c-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9990c-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9990c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9990c-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9990c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9990c-117">Peut</span><span class="sxs-lookup"><span data-stu-id="9990c-117">'T</span></span>

<span data-ttu-id="9990c-118">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="9990c-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9990c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9990c-119">See Also</span></span>

- [<span data-ttu-id="9990c-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="9990c-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="9990c-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="9990c-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="9990c-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="9990c-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)