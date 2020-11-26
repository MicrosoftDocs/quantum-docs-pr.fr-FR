---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Opération ApplyToRestA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 34cb5071dd939d0831e39bb8f1670670ae1fad31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208299"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="c0880-102">Opération ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="c0880-102">ApplyToRestA operation</span></span>

<span data-ttu-id="c0880-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c0880-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c0880-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0880-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0880-105">Applique une opération à tous les éléments à l’exception du premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="c0880-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="c0880-106">Description</span><span class="sxs-lookup"><span data-stu-id="c0880-106">Description</span></span>

<span data-ttu-id="c0880-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c0880-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c0880-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="c0880-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="c0880-109">OP : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="c0880-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c0880-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="c0880-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c0880-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="c0880-111">targets : 'T[]</span></span>

<span data-ttu-id="c0880-112">Tableau de cibles, dont tous les sauf le premier seront appliqués `op` .</span><span class="sxs-lookup"><span data-stu-id="c0880-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0880-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0880-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c0880-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c0880-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c0880-115">Peut</span><span class="sxs-lookup"><span data-stu-id="c0880-115">'T</span></span>

<span data-ttu-id="c0880-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="c0880-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0880-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c0880-117">See Also</span></span>

- [<span data-ttu-id="c0880-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="c0880-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="c0880-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="c0880-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="c0880-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="c0880-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)