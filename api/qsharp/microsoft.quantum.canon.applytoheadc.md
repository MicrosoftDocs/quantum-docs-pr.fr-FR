---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Opération ApplyToHeadC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3ff6c25837f1219dd456bf1739a2953ff72e2df9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704787"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="8abf3-102">Opération ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="8abf3-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="8abf3-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8abf3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8abf3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8abf3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8abf3-105">Applique une opération au premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="8abf3-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="8abf3-106">Description</span><span class="sxs-lookup"><span data-stu-id="8abf3-106">Description</span></span>

<span data-ttu-id="8abf3-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8abf3-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8abf3-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="8abf3-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="8abf3-109">OP : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8abf3-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="8abf3-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="8abf3-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8abf3-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="8abf3-111">targets : 'T[]</span></span>

<span data-ttu-id="8abf3-112">Tableau de cibles, auquel le premier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="8abf3-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8abf3-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8abf3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8abf3-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="8abf3-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8abf3-115">Peut</span><span class="sxs-lookup"><span data-stu-id="8abf3-115">'T</span></span>

<span data-ttu-id="8abf3-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="8abf3-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8abf3-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8abf3-117">See Also</span></span>

- [<span data-ttu-id="8abf3-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="8abf3-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="8abf3-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="8abf3-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="8abf3-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="8abf3-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)