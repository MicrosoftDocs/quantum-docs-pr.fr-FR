---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: Opération ApplyToRestCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: d2dc10803044980d53f80f0577d16cb14a2eb301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704683"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="46d77-102">Opération ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="46d77-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="46d77-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="46d77-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="46d77-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46d77-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46d77-105">Applique une opération à tous les éléments à l’exception du premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="46d77-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="46d77-106">Description</span><span class="sxs-lookup"><span data-stu-id="46d77-106">Description</span></span>

<span data-ttu-id="46d77-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="46d77-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="46d77-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="46d77-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="46d77-109">OP : 't [] = [> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="46d77-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="46d77-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="46d77-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="46d77-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="46d77-111">targets : 'T[]</span></span>

<span data-ttu-id="46d77-112">Tableau de cibles, dont tous les sauf le premier seront appliqués `op` .</span><span class="sxs-lookup"><span data-stu-id="46d77-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46d77-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46d77-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="46d77-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="46d77-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="46d77-115">Peut</span><span class="sxs-lookup"><span data-stu-id="46d77-115">'T</span></span>

<span data-ttu-id="46d77-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="46d77-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="46d77-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46d77-117">See Also</span></span>

- [<span data-ttu-id="46d77-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="46d77-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="46d77-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="46d77-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="46d77-120">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="46d77-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)