---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Opération ApplyToEachIndexCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704939"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="9618f-102">Opération ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="9618f-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="9618f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9618f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9618f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9618f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9618f-105">Applique une opération à qubit unique à chaque élément indexé dans un registre.</span><span class="sxs-lookup"><span data-stu-id="9618f-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="9618f-106">Le modificateur `CA` indique que l’opération à qubit unique est adjointable et contrôlable.</span><span class="sxs-lookup"><span data-stu-id="9618f-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9618f-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="9618f-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="9618f-108">singleElementOperation : ([int](xref:microsoft.quantum.lang-ref.int), 't) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="9618f-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9618f-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="9618f-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9618f-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="9618f-110">register : 'T[]</span></span>

<span data-ttu-id="9618f-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="9618f-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9618f-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9618f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9618f-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9618f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9618f-114">Peut</span><span class="sxs-lookup"><span data-stu-id="9618f-114">'T</span></span>

<span data-ttu-id="9618f-115">Cible sur laquelle fonctionne chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="9618f-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9618f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9618f-116">See Also</span></span>

- [<span data-ttu-id="9618f-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="9618f-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)