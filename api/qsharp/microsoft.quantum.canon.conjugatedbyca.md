---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: df29bcf555026bceb13d6896db12e13671a49b9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704331"
---
# <a name="conjugatedbyca-function"></a><span data-ttu-id="aec99-102">ConjugatedByCA fonction)</span><span class="sxs-lookup"><span data-stu-id="aec99-102">ConjugatedByCA function</span></span>

<span data-ttu-id="aec99-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aec99-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aec99-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aec99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aec99-105">En fonction des opérations externes et internes, retourne une nouvelle opération qui conjugue l’opération interne par l’opération externe.</span><span class="sxs-lookup"><span data-stu-id="aec99-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="aec99-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="aec99-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="aec99-107">outerOperation : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aec99-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aec99-108">L’opération $U $ qui doit être utilisée pour conjuguer $V $.</span><span class="sxs-lookup"><span data-stu-id="aec99-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="aec99-109">Notez que l’opération externe $U $ doit être adjointable, mais qu’elle n’a pas besoin d’être contrôlable.</span><span class="sxs-lookup"><span data-stu-id="aec99-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj--ctl"></a><span data-ttu-id="aec99-110">innerOperation : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="aec99-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="aec99-111">L’opération $V être conjuguée.</span><span class="sxs-lookup"><span data-stu-id="aec99-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="aec99-112">Sortie : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="aec99-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="aec99-113">Nouvelle opération dont l’action est représentée par le $U unitaire ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="aec99-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aec99-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="aec99-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aec99-115">Peut</span><span class="sxs-lookup"><span data-stu-id="aec99-115">'T</span></span>

<span data-ttu-id="aec99-116">Type de la cible sur laquelle les opérations internes et externes agissent.</span><span class="sxs-lookup"><span data-stu-id="aec99-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="aec99-117">Notes</span><span class="sxs-lookup"><span data-stu-id="aec99-117">Remarks</span></span>

<span data-ttu-id="aec99-118">L’opération externe est toujours supposée être adjointable, mais elle n’a pas besoin d’être contrôlable pour que l’opération combinée soit contrôlable.</span><span class="sxs-lookup"><span data-stu-id="aec99-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="aec99-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aec99-119">See Also</span></span>

- [<span data-ttu-id="aec99-120">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="aec99-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="aec99-121">Microsoft. Quantum. Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="aec99-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="aec99-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="aec99-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="aec99-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="aec99-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)