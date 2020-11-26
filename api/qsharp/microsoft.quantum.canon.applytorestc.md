---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Opération ApplyToRestC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 779c3831b2027a58f97dae9609e96d4d98247da7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208191"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="d4056-102">Opération ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="d4056-102">ApplyToRestC operation</span></span>

<span data-ttu-id="d4056-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d4056-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d4056-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4056-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4056-105">Applique une opération à tous les éléments à l’exception du premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="d4056-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="d4056-106">Description</span><span class="sxs-lookup"><span data-stu-id="d4056-106">Description</span></span>

<span data-ttu-id="d4056-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d4056-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d4056-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="d4056-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="d4056-109">OP : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="d4056-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d4056-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="d4056-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d4056-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="d4056-111">targets : 'T[]</span></span>

<span data-ttu-id="d4056-112">Tableau de cibles, dont tous les sauf le premier seront appliqués `op` .</span><span class="sxs-lookup"><span data-stu-id="d4056-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4056-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4056-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d4056-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d4056-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d4056-115">Peut</span><span class="sxs-lookup"><span data-stu-id="d4056-115">'T</span></span>

<span data-ttu-id="d4056-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="d4056-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4056-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4056-117">See Also</span></span>

- [<span data-ttu-id="d4056-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="d4056-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="d4056-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="d4056-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="d4056-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="d4056-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)