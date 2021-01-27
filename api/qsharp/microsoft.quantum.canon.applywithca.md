---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: Opération ApplyWithCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: a5ce7dc5ddfbb2fc06743d36614129c371850da2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841142"
---
# <a name="applywithca-operation"></a><span data-ttu-id="120c6-102">Opération ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="120c6-102">ApplyWithCA operation</span></span>

<span data-ttu-id="120c6-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="120c6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="120c6-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="120c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="120c6-105">À partir de deux opérations, applique une telle que conjuguée à l’autre.</span><span class="sxs-lookup"><span data-stu-id="120c6-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="120c6-106">Description</span><span class="sxs-lookup"><span data-stu-id="120c6-106">Description</span></span>

<span data-ttu-id="120c6-107">À partir de deux opérations, décrites respectivement par les opérateurs d’unités $U $ et $V $, les applique dans la séquence $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="120c6-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="120c6-108">Autrement dit, cette opération implémente l’opérateur unitaire donné par $V $ conjugué avec $U $.</span><span class="sxs-lookup"><span data-stu-id="120c6-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="120c6-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="120c6-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="120c6-110">outerOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="120c6-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="120c6-111">L’opération $U $ qui doit être utilisée pour conjuguer $V $.</span><span class="sxs-lookup"><span data-stu-id="120c6-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="120c6-112">Notez que l’opération externe $U $ doit être adjointable, mais qu’elle n’a pas besoin d’être contrôlable.</span><span class="sxs-lookup"><span data-stu-id="120c6-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="120c6-113">innerOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="120c6-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="120c6-114">L’opération $V être conjuguée.</span><span class="sxs-lookup"><span data-stu-id="120c6-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="120c6-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="120c6-115">target : 'T</span></span>

<span data-ttu-id="120c6-116">Entrée à fournir aux opérations externes et internes.</span><span class="sxs-lookup"><span data-stu-id="120c6-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="120c6-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="120c6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="120c6-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="120c6-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="120c6-119">Peut</span><span class="sxs-lookup"><span data-stu-id="120c6-119">'T</span></span>

<span data-ttu-id="120c6-120">Cible sur laquelle les opérations internes et externes agissent.</span><span class="sxs-lookup"><span data-stu-id="120c6-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="120c6-121">Notes</span><span class="sxs-lookup"><span data-stu-id="120c6-121">Remarks</span></span>

<span data-ttu-id="120c6-122">L’opération externe est toujours supposée être adjointable, mais elle n’a pas besoin d’être contrôlable pour que l’opération combinée soit contrôlable.</span><span class="sxs-lookup"><span data-stu-id="120c6-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="120c6-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="120c6-123">See Also</span></span>

- [<span data-ttu-id="120c6-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="120c6-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="120c6-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="120c6-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="120c6-126">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="120c6-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)