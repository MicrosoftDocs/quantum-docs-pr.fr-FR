---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Opération ApplyToEach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217864"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="23539-102">Opération ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="23539-102">ApplyToEach operation</span></span>

<span data-ttu-id="23539-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="23539-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="23539-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23539-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23539-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="23539-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="23539-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="23539-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="23539-107">singleElementOperation : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23539-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="23539-108">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="23539-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="23539-109">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="23539-109">register : 'T[]</span></span>

<span data-ttu-id="23539-110">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="23539-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="23539-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23539-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="23539-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="23539-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="23539-113">Peut</span><span class="sxs-lookup"><span data-stu-id="23539-113">'T</span></span>

<span data-ttu-id="23539-114">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="23539-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="23539-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="23539-115">See Also</span></span>

- [<span data-ttu-id="23539-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="23539-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="23539-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="23539-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="23539-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="23539-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)