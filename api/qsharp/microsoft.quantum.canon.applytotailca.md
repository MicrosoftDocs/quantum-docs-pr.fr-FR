---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Opération ApplyToTailCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: afb9eaa277814d7434b00a5c853a0c002190c1ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207851"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="55941-102">Opération ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="55941-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="55941-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="55941-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="55941-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55941-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55941-105">Applique une opération au dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="55941-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="55941-106">Description</span><span class="sxs-lookup"><span data-stu-id="55941-106">Description</span></span>

<span data-ttu-id="55941-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="55941-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="55941-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="55941-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="55941-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="55941-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="55941-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="55941-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="55941-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="55941-111">targets : 'T[]</span></span>

<span data-ttu-id="55941-112">Tableau de cibles auquel le dernier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="55941-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55941-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55941-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="55941-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="55941-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55941-115">Peut</span><span class="sxs-lookup"><span data-stu-id="55941-115">'T</span></span>

<span data-ttu-id="55941-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="55941-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="55941-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="55941-117">See Also</span></span>

- [<span data-ttu-id="55941-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="55941-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="55941-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="55941-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="55941-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="55941-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)