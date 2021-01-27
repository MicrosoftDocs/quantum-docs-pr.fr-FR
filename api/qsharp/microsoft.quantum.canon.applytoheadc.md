---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Opération ApplyToHeadC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850626"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="404da-102">Opération ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="404da-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="404da-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="404da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="404da-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="404da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="404da-105">Applique une opération au premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="404da-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="404da-106">Description</span><span class="sxs-lookup"><span data-stu-id="404da-106">Description</span></span>

<span data-ttu-id="404da-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="404da-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="404da-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="404da-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="404da-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="404da-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="404da-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="404da-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="404da-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="404da-111">targets : 'T[]</span></span>

<span data-ttu-id="404da-112">Tableau de cibles, auquel le premier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="404da-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="404da-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="404da-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="404da-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="404da-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="404da-115">Peut</span><span class="sxs-lookup"><span data-stu-id="404da-115">'T</span></span>

<span data-ttu-id="404da-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="404da-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="404da-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="404da-117">See Also</span></span>

- [<span data-ttu-id="404da-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="404da-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="404da-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="404da-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="404da-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="404da-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)