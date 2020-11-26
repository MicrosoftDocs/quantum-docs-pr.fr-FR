---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: Opération ApplyToTailC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5a68cae3fd122416cfd064e0078e03f5c00ab492
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217286"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="173af-102">Opération ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="173af-102">ApplyToTailC operation</span></span>

<span data-ttu-id="173af-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="173af-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="173af-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="173af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="173af-105">Applique une opération au dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="173af-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="173af-106">Description</span><span class="sxs-lookup"><span data-stu-id="173af-106">Description</span></span>

<span data-ttu-id="173af-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="173af-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="173af-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="173af-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="173af-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="173af-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="173af-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="173af-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="173af-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="173af-111">targets : 'T[]</span></span>

<span data-ttu-id="173af-112">Tableau de cibles auquel le dernier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="173af-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="173af-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="173af-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="173af-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="173af-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="173af-115">Peut</span><span class="sxs-lookup"><span data-stu-id="173af-115">'T</span></span>

<span data-ttu-id="173af-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="173af-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="173af-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="173af-117">See Also</span></span>

- [<span data-ttu-id="173af-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="173af-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="173af-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="173af-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="173af-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="173af-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)