---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Opération ApplyToMostC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a5927f6b296dd50afec8979c8e8ac22979b8a082
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704742"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="014c3-102">Opération ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="014c3-102">ApplyToMostC operation</span></span>

<span data-ttu-id="014c3-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="014c3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="014c3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="014c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="014c3-105">Applique une opération à tous les éléments à l’exception du dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="014c3-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="014c3-106">Description</span><span class="sxs-lookup"><span data-stu-id="014c3-106">Description</span></span>

<span data-ttu-id="014c3-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="014c3-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="014c3-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="014c3-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="014c3-109">OP : 't [] => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="014c3-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="014c3-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="014c3-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="014c3-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="014c3-111">targets : 'T[]</span></span>

<span data-ttu-id="014c3-112">Tableau de cibles, dont toutes les dernières sont appliquées `op` .</span><span class="sxs-lookup"><span data-stu-id="014c3-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="014c3-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="014c3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="014c3-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="014c3-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="014c3-115">Peut</span><span class="sxs-lookup"><span data-stu-id="014c3-115">'T</span></span>

<span data-ttu-id="014c3-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="014c3-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="014c3-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="014c3-117">See Also</span></span>

- [<span data-ttu-id="014c3-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="014c3-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="014c3-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="014c3-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="014c3-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="014c3-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)