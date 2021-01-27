---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Opération ApplyToHead
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841334"
---
# <a name="applytohead-operation"></a><span data-ttu-id="6a09b-102">Opération ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="6a09b-102">ApplyToHead operation</span></span>

<span data-ttu-id="6a09b-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a09b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a09b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a09b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a09b-105">Applique une opération au premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="6a09b-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6a09b-106">Description</span><span class="sxs-lookup"><span data-stu-id="6a09b-106">Description</span></span>

<span data-ttu-id="6a09b-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="6a09b-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6a09b-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="6a09b-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="6a09b-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a09b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6a09b-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="6a09b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6a09b-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="6a09b-111">targets : 'T[]</span></span>

<span data-ttu-id="6a09b-112">Tableau de cibles, auquel le premier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="6a09b-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a09b-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a09b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6a09b-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6a09b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a09b-115">Peut</span><span class="sxs-lookup"><span data-stu-id="6a09b-115">'T</span></span>

<span data-ttu-id="6a09b-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="6a09b-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="6a09b-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="6a09b-117">Example</span></span>

<span data-ttu-id="6a09b-118">Les extraits de code Q # suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="6a09b-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="6a09b-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6a09b-119">See Also</span></span>

- [<span data-ttu-id="6a09b-120">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="6a09b-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="6a09b-121">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="6a09b-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="6a09b-122">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="6a09b-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)