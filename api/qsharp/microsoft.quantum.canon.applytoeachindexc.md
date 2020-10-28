---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Opération ApplyToEachIndexC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704947"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="bfd73-102">Opération ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="bfd73-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="bfd73-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bfd73-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bfd73-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bfd73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bfd73-105">Applique une opération à qubit unique à chaque élément indexé dans un registre.</span><span class="sxs-lookup"><span data-stu-id="bfd73-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="bfd73-106">Le modificateur `C` indique que l’opération de qubit simple est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="bfd73-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bfd73-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="bfd73-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-ctl"></a><span data-ttu-id="bfd73-108">singleElementOperation : ([int](xref:microsoft.quantum.lang-ref.int), 't) => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bfd73-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="bfd73-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="bfd73-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bfd73-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="bfd73-110">register : 'T[]</span></span>

<span data-ttu-id="bfd73-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="bfd73-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bfd73-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bfd73-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bfd73-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="bfd73-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bfd73-114">Peut</span><span class="sxs-lookup"><span data-stu-id="bfd73-114">'T</span></span>

<span data-ttu-id="bfd73-115">Cible sur laquelle fonctionne chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="bfd73-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfd73-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bfd73-116">See Also</span></span>

- [<span data-ttu-id="bfd73-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="bfd73-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)