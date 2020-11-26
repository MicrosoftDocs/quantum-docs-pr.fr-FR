---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Opération ApplyToTailA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 2cacac14ad6e5003f1a50d9b84c4e0f96950dd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207919"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="4a70a-102">Opération ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="4a70a-102">ApplyToTailA operation</span></span>

<span data-ttu-id="4a70a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a70a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a70a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a70a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a70a-105">Applique une opération au dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="4a70a-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="4a70a-106">Description</span><span class="sxs-lookup"><span data-stu-id="4a70a-106">Description</span></span>

<span data-ttu-id="4a70a-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4a70a-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4a70a-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="4a70a-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="4a70a-109">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="4a70a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="4a70a-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="4a70a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4a70a-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="4a70a-111">targets : 'T[]</span></span>

<span data-ttu-id="4a70a-112">Tableau de cibles auquel le dernier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="4a70a-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a70a-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a70a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4a70a-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4a70a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a70a-115">Peut</span><span class="sxs-lookup"><span data-stu-id="4a70a-115">'T</span></span>

<span data-ttu-id="4a70a-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="4a70a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a70a-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a70a-117">See Also</span></span>

- [<span data-ttu-id="4a70a-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="4a70a-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="4a70a-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="4a70a-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="4a70a-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="4a70a-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)