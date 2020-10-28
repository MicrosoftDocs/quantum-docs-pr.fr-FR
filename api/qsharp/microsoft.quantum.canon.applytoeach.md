---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Opération ApplyToEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704982"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="bbb9a-102">Opération ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="bbb9a-102">ApplyToEach operation</span></span>

<span data-ttu-id="bbb9a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bbb9a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bbb9a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bbb9a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bbb9a-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="bbb9a-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bbb9a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="bbb9a-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="bbb9a-107">singleElementOperation : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bbb9a-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bbb9a-108">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="bbb9a-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bbb9a-109">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="bbb9a-109">register : 'T[]</span></span>

<span data-ttu-id="bbb9a-110">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="bbb9a-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bbb9a-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bbb9a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bbb9a-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="bbb9a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bbb9a-113">Peut</span><span class="sxs-lookup"><span data-stu-id="bbb9a-113">'T</span></span>

<span data-ttu-id="bbb9a-114">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="bbb9a-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbb9a-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bbb9a-115">See Also</span></span>

- [<span data-ttu-id="bbb9a-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="bbb9a-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="bbb9a-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="bbb9a-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="bbb9a-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="bbb9a-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)