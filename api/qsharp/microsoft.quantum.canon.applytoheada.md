---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Opération ApplyToHeadA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704790"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="4be7d-102">Opération ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="4be7d-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="4be7d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4be7d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4be7d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4be7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4be7d-105">Applique une opération au premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="4be7d-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4be7d-106">Description</span><span class="sxs-lookup"><span data-stu-id="4be7d-106">Description</span></span>

<span data-ttu-id="4be7d-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4be7d-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4be7d-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="4be7d-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="4be7d-109">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4be7d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4be7d-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="4be7d-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4be7d-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="4be7d-111">targets : 'T[]</span></span>

<span data-ttu-id="4be7d-112">Tableau de cibles, auquel le premier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="4be7d-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4be7d-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4be7d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4be7d-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4be7d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4be7d-115">Peut</span><span class="sxs-lookup"><span data-stu-id="4be7d-115">'T</span></span>

<span data-ttu-id="4be7d-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="4be7d-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4be7d-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4be7d-117">See Also</span></span>

- [<span data-ttu-id="4be7d-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="4be7d-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="4be7d-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="4be7d-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="4be7d-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="4be7d-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)