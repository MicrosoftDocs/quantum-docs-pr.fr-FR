---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Opération ApplyToEachIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704955"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="9ce7a-102">Opération ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="9ce7a-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="9ce7a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ce7a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ce7a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ce7a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ce7a-105">Applique une opération à qubit unique à chaque élément indexé dans un registre.</span><span class="sxs-lookup"><span data-stu-id="9ce7a-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9ce7a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9ce7a-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="9ce7a-107">singleElementOperation : ([int](xref:microsoft.quantum.lang-ref.int), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ce7a-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9ce7a-108">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="9ce7a-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9ce7a-109">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="9ce7a-109">register : 'T[]</span></span>

<span data-ttu-id="9ce7a-110">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="9ce7a-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ce7a-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ce7a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9ce7a-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9ce7a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ce7a-113">Peut</span><span class="sxs-lookup"><span data-stu-id="9ce7a-113">'T</span></span>

<span data-ttu-id="9ce7a-114">Cible sur laquelle fonctionne chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="9ce7a-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ce7a-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ce7a-115">See Also</span></span>

- [<span data-ttu-id="9ce7a-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="9ce7a-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="9ce7a-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="9ce7a-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="9ce7a-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="9ce7a-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="9ce7a-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="9ce7a-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)