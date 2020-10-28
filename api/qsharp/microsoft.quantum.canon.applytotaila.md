---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Opération ApplyToTailA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704630"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="7e5ac-102">Opération ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="7e5ac-102">ApplyToTailA operation</span></span>

<span data-ttu-id="7e5ac-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7e5ac-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7e5ac-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e5ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e5ac-105">Applique une opération au dernier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="7e5ac-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="7e5ac-106">Description</span><span class="sxs-lookup"><span data-stu-id="7e5ac-106">Description</span></span>

<span data-ttu-id="7e5ac-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="7e5ac-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="7e5ac-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="7e5ac-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="7e5ac-109">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e5ac-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7e5ac-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="7e5ac-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="7e5ac-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="7e5ac-111">targets : 'T[]</span></span>

<span data-ttu-id="7e5ac-112">Tableau de cibles auquel le dernier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="7e5ac-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e5ac-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e5ac-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7e5ac-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7e5ac-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7e5ac-115">Peut</span><span class="sxs-lookup"><span data-stu-id="7e5ac-115">'T</span></span>

<span data-ttu-id="7e5ac-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="7e5ac-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e5ac-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e5ac-117">See Also</span></span>

- [<span data-ttu-id="7e5ac-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="7e5ac-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="7e5ac-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="7e5ac-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="7e5ac-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="7e5ac-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)