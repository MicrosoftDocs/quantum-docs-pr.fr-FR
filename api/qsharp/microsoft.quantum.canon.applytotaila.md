---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Opération ApplyToTailA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5ca22be7a38d466f9413977de663f10606171dea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841182"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="1b6c9-102">Opération ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="1b6c9-102">ApplyToTailA operation</span></span>

<span data-ttu-id="1b6c9-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1b6c9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1b6c9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b6c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b6c9-105">Applique une opération au dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="1b6c9-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="1b6c9-106">Description</span><span class="sxs-lookup"><span data-stu-id="1b6c9-106">Description</span></span>

<span data-ttu-id="1b6c9-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="1b6c9-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="1b6c9-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="1b6c9-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="1b6c9-109">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="1b6c9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1b6c9-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1b6c9-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1b6c9-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="1b6c9-111">targets : 'T[]</span></span>

<span data-ttu-id="1b6c9-112">Tableau de cibles auquel le dernier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="1b6c9-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b6c9-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b6c9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1b6c9-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1b6c9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b6c9-115">Peut</span><span class="sxs-lookup"><span data-stu-id="1b6c9-115">'T</span></span>

<span data-ttu-id="1b6c9-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1b6c9-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b6c9-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b6c9-117">See Also</span></span>

- [<span data-ttu-id="1b6c9-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="1b6c9-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="1b6c9-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="1b6c9-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="1b6c9-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="1b6c9-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)