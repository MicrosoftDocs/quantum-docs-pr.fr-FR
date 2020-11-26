---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Opération ApplyToMostC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: af55093e44ce023c9e8b7e478730f4c527cf6d32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208463"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="1162b-102">Opération ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="1162b-102">ApplyToMostC operation</span></span>

<span data-ttu-id="1162b-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1162b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1162b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1162b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1162b-105">Applique une opération à tous les éléments à l’exception du dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="1162b-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="1162b-106">Description</span><span class="sxs-lookup"><span data-stu-id="1162b-106">Description</span></span>

<span data-ttu-id="1162b-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="1162b-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="1162b-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="1162b-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="1162b-109">OP : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="1162b-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1162b-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1162b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1162b-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="1162b-111">targets : 'T[]</span></span>

<span data-ttu-id="1162b-112">Tableau de cibles, dont toutes les dernières sont appliquées `op` .</span><span class="sxs-lookup"><span data-stu-id="1162b-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1162b-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1162b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1162b-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1162b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1162b-115">Peut</span><span class="sxs-lookup"><span data-stu-id="1162b-115">'T</span></span>

<span data-ttu-id="1162b-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1162b-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1162b-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1162b-117">See Also</span></span>

- [<span data-ttu-id="1162b-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="1162b-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="1162b-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="1162b-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="1162b-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="1162b-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)