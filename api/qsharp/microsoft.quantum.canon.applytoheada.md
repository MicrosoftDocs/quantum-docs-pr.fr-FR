---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Opération ApplyToHeadA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208633"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="44dab-102">Opération ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="44dab-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="44dab-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="44dab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="44dab-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44dab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44dab-105">Applique une opération au premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="44dab-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="44dab-106">Description</span><span class="sxs-lookup"><span data-stu-id="44dab-106">Description</span></span>

<span data-ttu-id="44dab-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="44dab-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="44dab-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="44dab-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="44dab-109">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="44dab-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="44dab-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="44dab-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="44dab-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="44dab-111">targets : 'T[]</span></span>

<span data-ttu-id="44dab-112">Tableau de cibles, auquel le premier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="44dab-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44dab-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44dab-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="44dab-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="44dab-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="44dab-115">Peut</span><span class="sxs-lookup"><span data-stu-id="44dab-115">'T</span></span>

<span data-ttu-id="44dab-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="44dab-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="44dab-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="44dab-117">See Also</span></span>

- [<span data-ttu-id="44dab-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="44dab-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="44dab-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="44dab-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="44dab-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="44dab-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)