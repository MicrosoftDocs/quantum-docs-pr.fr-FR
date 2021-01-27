---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Opération ApplyToMost
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850588"
---
# <a name="applytomost-operation"></a><span data-ttu-id="096be-102">Opération ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="096be-102">ApplyToMost operation</span></span>

<span data-ttu-id="096be-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="096be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="096be-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="096be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="096be-105">Applique une opération à tous les éléments à l’exception du dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="096be-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="096be-106">Description</span><span class="sxs-lookup"><span data-stu-id="096be-106">Description</span></span>

<span data-ttu-id="096be-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="096be-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="096be-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="096be-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="096be-109">OP : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="096be-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="096be-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="096be-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="096be-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="096be-111">targets : 'T[]</span></span>

<span data-ttu-id="096be-112">Tableau de cibles, dont toutes les dernières sont appliquées `op` .</span><span class="sxs-lookup"><span data-stu-id="096be-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="096be-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="096be-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="096be-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="096be-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="096be-115">Peut</span><span class="sxs-lookup"><span data-stu-id="096be-115">'T</span></span>

<span data-ttu-id="096be-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="096be-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="096be-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="096be-117">Example</span></span>

<span data-ttu-id="096be-118">Les extraits de code Q # suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="096be-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="096be-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="096be-119">See Also</span></span>

- [<span data-ttu-id="096be-120">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="096be-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="096be-121">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="096be-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="096be-122">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="096be-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)