---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: Opération ApplyToEachA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217796"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="4a864-102">Opération ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="4a864-102">ApplyToEachA operation</span></span>

<span data-ttu-id="4a864-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a864-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a864-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a864-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a864-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="4a864-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="4a864-106">Le modificateur `A` indique que l’opération à qubit unique est adjointable.</span><span class="sxs-lookup"><span data-stu-id="4a864-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="4a864-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="4a864-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="4a864-108">singleElementOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="4a864-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="4a864-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="4a864-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="4a864-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="4a864-110">register : 'T[]</span></span>

<span data-ttu-id="4a864-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="4a864-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a864-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a864-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4a864-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4a864-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a864-114">Peut</span><span class="sxs-lookup"><span data-stu-id="4a864-114">'T</span></span>

<span data-ttu-id="4a864-115">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="4a864-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a864-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a864-116">See Also</span></span>

- [<span data-ttu-id="4a864-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="4a864-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)