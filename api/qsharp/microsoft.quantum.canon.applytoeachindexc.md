---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Opération ApplyToEachIndexC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850820"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="3ec7f-102">Opération ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="3ec7f-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="3ec7f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3ec7f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3ec7f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ec7f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ec7f-105">Applique une opération à qubit unique à chaque élément indexé dans un registre.</span><span class="sxs-lookup"><span data-stu-id="3ec7f-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="3ec7f-106">Le modificateur `C` indique que l’opération de qubit simple est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="3ec7f-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="3ec7f-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="3ec7f-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="3ec7f-108">singleElementOperation : ([int](xref:microsoft.quantum.lang-ref.int), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="3ec7f-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3ec7f-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="3ec7f-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="3ec7f-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="3ec7f-110">register : 'T[]</span></span>

<span data-ttu-id="3ec7f-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="3ec7f-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ec7f-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ec7f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3ec7f-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="3ec7f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3ec7f-114">Peut</span><span class="sxs-lookup"><span data-stu-id="3ec7f-114">'T</span></span>

<span data-ttu-id="3ec7f-115">Cible sur laquelle fonctionne chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="3ec7f-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ec7f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3ec7f-116">See Also</span></span>

- [<span data-ttu-id="3ec7f-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="3ec7f-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)