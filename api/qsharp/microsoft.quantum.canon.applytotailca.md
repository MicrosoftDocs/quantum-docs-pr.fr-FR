---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Opération ApplyToTailCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841196"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="47c31-102">Opération ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="47c31-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="47c31-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="47c31-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="47c31-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47c31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47c31-105">Applique une opération au dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="47c31-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="47c31-106">Description</span><span class="sxs-lookup"><span data-stu-id="47c31-106">Description</span></span>

<span data-ttu-id="47c31-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="47c31-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="47c31-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="47c31-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="47c31-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="47c31-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="47c31-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="47c31-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="47c31-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="47c31-111">targets : 'T[]</span></span>

<span data-ttu-id="47c31-112">Tableau de cibles auquel le dernier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="47c31-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47c31-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47c31-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="47c31-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="47c31-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47c31-115">Peut</span><span class="sxs-lookup"><span data-stu-id="47c31-115">'T</span></span>

<span data-ttu-id="47c31-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="47c31-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="47c31-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47c31-117">See Also</span></span>

- [<span data-ttu-id="47c31-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="47c31-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="47c31-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="47c31-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="47c31-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="47c31-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)