---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Opération ApplyToEachCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: c85b33760eba8d10d9650be2f8306e4afdd1f307
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841490"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="819c4-102">Opération ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="819c4-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="819c4-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="819c4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="819c4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="819c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="819c4-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="819c4-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="819c4-106">Le modificateur `CA` indique que l’opération de qubit simple est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="819c4-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="819c4-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="819c4-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="819c4-108">singleElementOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="819c4-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="819c4-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="819c4-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="819c4-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="819c4-110">register : 'T[]</span></span>

<span data-ttu-id="819c4-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="819c4-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="819c4-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="819c4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="819c4-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="819c4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="819c4-114">Peut</span><span class="sxs-lookup"><span data-stu-id="819c4-114">'T</span></span>

<span data-ttu-id="819c4-115">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="819c4-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="819c4-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="819c4-116">Example</span></span>

<span data-ttu-id="819c4-117">Préparez un état de trois-qubit $ \ket{+} $ :</span><span class="sxs-lookup"><span data-stu-id="819c4-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="819c4-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="819c4-118">See Also</span></span>

- [<span data-ttu-id="819c4-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="819c4-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)