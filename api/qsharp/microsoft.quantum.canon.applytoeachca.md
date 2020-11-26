---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Opération ApplyToEachCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217745"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="7b2e9-102">Opération ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="7b2e9-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="7b2e9-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7b2e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7b2e9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b2e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b2e9-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="7b2e9-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="7b2e9-106">Le modificateur `CA` indique que l’opération de qubit simple est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="7b2e9-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7b2e9-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="7b2e9-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="7b2e9-108">singleElementOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="7b2e9-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7b2e9-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="7b2e9-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="7b2e9-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="7b2e9-110">register : 'T[]</span></span>

<span data-ttu-id="7b2e9-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="7b2e9-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7b2e9-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b2e9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7b2e9-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7b2e9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b2e9-114">Peut</span><span class="sxs-lookup"><span data-stu-id="7b2e9-114">'T</span></span>

<span data-ttu-id="7b2e9-115">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="7b2e9-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b2e9-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b2e9-116">See Also</span></span>

- [<span data-ttu-id="7b2e9-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="7b2e9-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)