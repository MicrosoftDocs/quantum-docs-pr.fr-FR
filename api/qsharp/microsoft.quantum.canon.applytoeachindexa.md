---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Opération ApplyToEachIndexA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850827"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="9660f-102">Opération ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="9660f-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="9660f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9660f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9660f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9660f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9660f-105">Applique une opération à qubit unique à chaque élément indexé dans un registre.</span><span class="sxs-lookup"><span data-stu-id="9660f-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="9660f-106">Le modificateur `A` indique que l’opération à qubit unique est adjointable.</span><span class="sxs-lookup"><span data-stu-id="9660f-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9660f-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="9660f-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="9660f-108">singleElementOperation : ([int](xref:microsoft.quantum.lang-ref.int), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="9660f-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9660f-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="9660f-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9660f-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="9660f-110">register : 'T[]</span></span>

<span data-ttu-id="9660f-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="9660f-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9660f-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9660f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9660f-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9660f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9660f-114">Peut</span><span class="sxs-lookup"><span data-stu-id="9660f-114">'T</span></span>

<span data-ttu-id="9660f-115">Cible sur laquelle fonctionne chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="9660f-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9660f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9660f-116">See Also</span></span>

- [<span data-ttu-id="9660f-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="9660f-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)