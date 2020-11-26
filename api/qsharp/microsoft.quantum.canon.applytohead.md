---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Opération ApplyToHead
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217337"
---
# <a name="applytohead-operation"></a><span data-ttu-id="4cecc-102">Opération ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="4cecc-102">ApplyToHead operation</span></span>

<span data-ttu-id="4cecc-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4cecc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4cecc-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4cecc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4cecc-105">Applique une opération au premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="4cecc-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4cecc-106">Description</span><span class="sxs-lookup"><span data-stu-id="4cecc-106">Description</span></span>

<span data-ttu-id="4cecc-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4cecc-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4cecc-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="4cecc-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4cecc-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4cecc-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4cecc-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="4cecc-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4cecc-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="4cecc-111">targets : 'T[]</span></span>

<span data-ttu-id="4cecc-112">Tableau de cibles, auquel le premier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="4cecc-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4cecc-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4cecc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4cecc-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4cecc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4cecc-115">Peut</span><span class="sxs-lookup"><span data-stu-id="4cecc-115">'T</span></span>

<span data-ttu-id="4cecc-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="4cecc-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cecc-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4cecc-117">See Also</span></span>

- [<span data-ttu-id="4cecc-118">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="4cecc-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="4cecc-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="4cecc-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="4cecc-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="4cecc-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)