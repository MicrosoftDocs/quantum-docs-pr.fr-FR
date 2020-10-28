---
uid: Microsoft.Quantum.Canon.NoOp
title: Opération NoOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703948"
---
# <a name="noop-operation"></a><span data-ttu-id="f34b0-102">Opération NoOp</span><span class="sxs-lookup"><span data-stu-id="f34b0-102">NoOp operation</span></span>

<span data-ttu-id="f34b0-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f34b0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f34b0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f34b0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f34b0-105">Exécute l’opération d’identité (no-op) sur un argument.</span><span class="sxs-lookup"><span data-stu-id="f34b0-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="f34b0-106">Description</span><span class="sxs-lookup"><span data-stu-id="f34b0-106">Description</span></span>

<span data-ttu-id="f34b0-107">Cette opération accepte une valeur de n’importe quel type et ne fait rien d’autre.</span><span class="sxs-lookup"><span data-stu-id="f34b0-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="f34b0-108">Cela peut être utile lorsqu’une entrée d’un type d’opération est attendue, mais qu’aucune action ne doit être effectuée.</span><span class="sxs-lookup"><span data-stu-id="f34b0-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="f34b0-109">Par exemple, si un syndrome de correction d’erreur particulier indique qu’aucune erreur ne s’est produite, `NoOp<Qubit[]>` il peut s’agir de la bonne procédure de récupération.</span><span class="sxs-lookup"><span data-stu-id="f34b0-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="f34b0-110">De même, si une opération attend une procédure de préparation d’État comme entrée, `NoOp<Qubit[]>` peut être utilisé pour préparer l’État $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="f34b0-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="f34b0-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="f34b0-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="f34b0-112">entrée : 't</span><span class="sxs-lookup"><span data-stu-id="f34b0-112">input : 'T</span></span>

<span data-ttu-id="f34b0-113">Valeur à ignorer.</span><span class="sxs-lookup"><span data-stu-id="f34b0-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f34b0-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f34b0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f34b0-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="f34b0-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f34b0-116">Peut</span><span class="sxs-lookup"><span data-stu-id="f34b0-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="f34b0-117">Notes</span><span class="sxs-lookup"><span data-stu-id="f34b0-117">Remarks</span></span>

<span data-ttu-id="f34b0-118">Dans presque tous les cas, le paramètre de type `NoOp` doit être spécifié explicitement.</span><span class="sxs-lookup"><span data-stu-id="f34b0-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="f34b0-119">Par exemple, `NoOp<Qubit>` est identique à <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="f34b0-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="f34b0-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f34b0-120">See Also</span></span>

- [<span data-ttu-id="f34b0-121">Microsoft. Quantum. Intrinsic. I</span><span class="sxs-lookup"><span data-stu-id="f34b0-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)