---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Opération ApplyToEachC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217779"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="696f5-102">Opération ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="696f5-102">ApplyToEachC operation</span></span>

<span data-ttu-id="696f5-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="696f5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="696f5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="696f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="696f5-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="696f5-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="696f5-106">Le modificateur `C` indique que l’opération de qubit simple est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="696f5-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="696f5-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="696f5-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="696f5-108">singleElementOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="696f5-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="696f5-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="696f5-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="696f5-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="696f5-110">register : 'T[]</span></span>

<span data-ttu-id="696f5-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="696f5-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="696f5-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="696f5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="696f5-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="696f5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="696f5-114">Peut</span><span class="sxs-lookup"><span data-stu-id="696f5-114">'T</span></span>

<span data-ttu-id="696f5-115">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="696f5-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="696f5-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="696f5-116">See Also</span></span>

- [<span data-ttu-id="696f5-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="696f5-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)