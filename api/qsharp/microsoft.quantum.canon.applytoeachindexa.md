---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Opération ApplyToEachIndexA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704950"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="bf9f3-102">Opération ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="bf9f3-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="bf9f3-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bf9f3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bf9f3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf9f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf9f3-105">Applique une opération à qubit unique à chaque élément indexé dans un registre.</span><span class="sxs-lookup"><span data-stu-id="bf9f3-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="bf9f3-106">Le modificateur `A` indique que l’opération à qubit unique est adjointable.</span><span class="sxs-lookup"><span data-stu-id="bf9f3-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bf9f3-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="bf9f3-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj"></a><span data-ttu-id="bf9f3-108">singleElementOperation : ([int](xref:microsoft.quantum.lang-ref.int), 't) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf9f3-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="bf9f3-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="bf9f3-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bf9f3-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="bf9f3-110">register : 'T[]</span></span>

<span data-ttu-id="bf9f3-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="bf9f3-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf9f3-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf9f3-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bf9f3-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="bf9f3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf9f3-114">Peut</span><span class="sxs-lookup"><span data-stu-id="bf9f3-114">'T</span></span>

<span data-ttu-id="bf9f3-115">Cible sur laquelle fonctionne chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="bf9f3-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf9f3-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf9f3-116">See Also</span></span>

- [<span data-ttu-id="bf9f3-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="bf9f3-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)