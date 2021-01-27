---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Opération ApplyToMostCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 0a80c23e0c6ff45083c192579dd8301d2277cef2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841315"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="c76b4-102">Opération ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="c76b4-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="c76b4-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c76b4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c76b4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c76b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c76b4-105">Applique une opération à tous les éléments à l’exception du dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="c76b4-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c76b4-106">Description</span><span class="sxs-lookup"><span data-stu-id="c76b4-106">Description</span></span>

<span data-ttu-id="c76b4-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c76b4-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c76b4-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="c76b4-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="c76b4-109">OP : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c76b4-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c76b4-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="c76b4-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c76b4-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="c76b4-111">targets : 'T[]</span></span>

<span data-ttu-id="c76b4-112">Tableau de cibles, dont toutes les dernières sont appliquées `op` .</span><span class="sxs-lookup"><span data-stu-id="c76b4-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c76b4-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c76b4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c76b4-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c76b4-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c76b4-115">Peut</span><span class="sxs-lookup"><span data-stu-id="c76b4-115">'T</span></span>

<span data-ttu-id="c76b4-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="c76b4-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c76b4-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c76b4-117">See Also</span></span>

- [<span data-ttu-id="c76b4-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="c76b4-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="c76b4-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="c76b4-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="c76b4-120">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="c76b4-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)