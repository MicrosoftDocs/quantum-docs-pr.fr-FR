---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Opération ApplyToEachC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704966"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="e40c2-102">Opération ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="e40c2-102">ApplyToEachC operation</span></span>

<span data-ttu-id="e40c2-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e40c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e40c2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e40c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e40c2-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="e40c2-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="e40c2-106">Le modificateur `C` indique que l’opération de qubit simple est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="e40c2-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e40c2-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="e40c2-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="e40c2-108">singleElementOperation : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e40c2-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e40c2-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="e40c2-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="e40c2-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="e40c2-110">register : 'T[]</span></span>

<span data-ttu-id="e40c2-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="e40c2-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e40c2-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e40c2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e40c2-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e40c2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e40c2-114">Peut</span><span class="sxs-lookup"><span data-stu-id="e40c2-114">'T</span></span>

<span data-ttu-id="e40c2-115">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="e40c2-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="e40c2-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e40c2-116">See Also</span></span>

- [<span data-ttu-id="e40c2-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="e40c2-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)