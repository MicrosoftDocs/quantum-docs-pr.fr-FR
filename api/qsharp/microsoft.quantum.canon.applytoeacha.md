---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: Opération ApplyToEachA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704974"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="81e49-102">Opération ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="81e49-102">ApplyToEachA operation</span></span>

<span data-ttu-id="81e49-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="81e49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="81e49-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81e49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81e49-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="81e49-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="81e49-106">Le modificateur `A` indique que l’opération à qubit unique est adjointable.</span><span class="sxs-lookup"><span data-stu-id="81e49-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="81e49-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="81e49-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj"></a><span data-ttu-id="81e49-108">singleElementOperation : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81e49-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="81e49-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="81e49-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="81e49-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="81e49-110">register : 'T[]</span></span>

<span data-ttu-id="81e49-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="81e49-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81e49-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81e49-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="81e49-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="81e49-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="81e49-114">Peut</span><span class="sxs-lookup"><span data-stu-id="81e49-114">'T</span></span>

<span data-ttu-id="81e49-115">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="81e49-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="81e49-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81e49-116">See Also</span></span>

- [<span data-ttu-id="81e49-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="81e49-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)