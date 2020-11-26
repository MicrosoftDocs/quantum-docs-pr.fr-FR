---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: ConjugatedByC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 1aa471a0f9039151d130bd52a026f4c1a0765e32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216674"
---
# <a name="conjugatedbyc-function"></a><span data-ttu-id="35f34-102">ConjugatedByC fonction)</span><span class="sxs-lookup"><span data-stu-id="35f34-102">ConjugatedByC function</span></span>

<span data-ttu-id="35f34-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="35f34-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="35f34-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35f34-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35f34-105">En fonction des opérations externes et internes, retourne une nouvelle opération qui conjugue l’opération interne par l’opération externe.</span><span class="sxs-lookup"><span data-stu-id="35f34-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="35f34-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="35f34-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="35f34-107">outerOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="35f34-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="35f34-108">L’opération $U $ qui doit être utilisée pour conjuguer $V $.</span><span class="sxs-lookup"><span data-stu-id="35f34-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="35f34-109">Notez que l’opération externe $U $ doit être adjointable, mais qu’elle n’a pas besoin d’être contrôlable.</span><span class="sxs-lookup"><span data-stu-id="35f34-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-ctl"></a><span data-ttu-id="35f34-110">innerOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="35f34-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="35f34-111">L’opération $V être conjuguée.</span><span class="sxs-lookup"><span data-stu-id="35f34-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="35f34-112">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="35f34-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="35f34-113">Nouvelle opération dont l’action est représentée par le $U unitaire ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="35f34-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="35f34-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="35f34-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35f34-115">Peut</span><span class="sxs-lookup"><span data-stu-id="35f34-115">'T</span></span>

<span data-ttu-id="35f34-116">Type de la cible sur laquelle les opérations internes et externes agissent.</span><span class="sxs-lookup"><span data-stu-id="35f34-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="35f34-117">Notes</span><span class="sxs-lookup"><span data-stu-id="35f34-117">Remarks</span></span>

<span data-ttu-id="35f34-118">L’opération externe est toujours supposée être adjointable, mais elle n’a pas besoin d’être contrôlable pour que l’opération combinée soit contrôlable.</span><span class="sxs-lookup"><span data-stu-id="35f34-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="35f34-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35f34-119">See Also</span></span>

- [<span data-ttu-id="35f34-120">Microsoft. Quantum. Canon. ConjugatedBy</span><span class="sxs-lookup"><span data-stu-id="35f34-120">Microsoft.Quantum.Canon.ConjugatedBy</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [<span data-ttu-id="35f34-121">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="35f34-121">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="35f34-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="35f34-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="35f34-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="35f34-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)