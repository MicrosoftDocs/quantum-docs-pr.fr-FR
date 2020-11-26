---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Opération ApplyToMost
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7e7824b431ccff644cf5cc53145163327eb8ad36
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208531"
---
# <a name="applytomost-operation"></a><span data-ttu-id="1dac8-102">Opération ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="1dac8-102">ApplyToMost operation</span></span>

<span data-ttu-id="1dac8-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1dac8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1dac8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1dac8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1dac8-105">Applique une opération à tous les éléments à l’exception du dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="1dac8-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="1dac8-106">Description</span><span class="sxs-lookup"><span data-stu-id="1dac8-106">Description</span></span>

<span data-ttu-id="1dac8-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="1dac8-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="1dac8-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="1dac8-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="1dac8-109">OP : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1dac8-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1dac8-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1dac8-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1dac8-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="1dac8-111">targets : 'T[]</span></span>

<span data-ttu-id="1dac8-112">Tableau de cibles, dont toutes les dernières sont appliquées `op` .</span><span class="sxs-lookup"><span data-stu-id="1dac8-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1dac8-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1dac8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1dac8-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1dac8-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1dac8-115">Peut</span><span class="sxs-lookup"><span data-stu-id="1dac8-115">'T</span></span>

<span data-ttu-id="1dac8-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1dac8-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dac8-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1dac8-117">See Also</span></span>

- [<span data-ttu-id="1dac8-118">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="1dac8-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="1dac8-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="1dac8-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="1dac8-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="1dac8-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)