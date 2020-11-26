---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Opération ApplyToEachIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 746bc19f7a137ef476a25abdabc4737ed6727ff2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217609"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="32b2c-102">Opération ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="32b2c-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="32b2c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="32b2c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="32b2c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32b2c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32b2c-105">Applique une opération à qubit unique à chaque élément indexé dans un registre.</span><span class="sxs-lookup"><span data-stu-id="32b2c-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="32b2c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="32b2c-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="32b2c-107">singleElementOperation : ([int](xref:microsoft.quantum.lang-ref.int), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32b2c-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="32b2c-108">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="32b2c-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="32b2c-109">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="32b2c-109">register : 'T[]</span></span>

<span data-ttu-id="32b2c-110">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="32b2c-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="32b2c-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32b2c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="32b2c-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="32b2c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="32b2c-113">Peut</span><span class="sxs-lookup"><span data-stu-id="32b2c-113">'T</span></span>

<span data-ttu-id="32b2c-114">Cible sur laquelle fonctionne chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="32b2c-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="32b2c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32b2c-115">See Also</span></span>

- [<span data-ttu-id="32b2c-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="32b2c-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="32b2c-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="32b2c-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="32b2c-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="32b2c-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="32b2c-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="32b2c-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)