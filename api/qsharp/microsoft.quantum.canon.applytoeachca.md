---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Opération ApplyToEachCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704958"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="1fedd-102">Opération ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="1fedd-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="1fedd-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1fedd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1fedd-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1fedd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1fedd-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="1fedd-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="1fedd-106">Le modificateur `CA` indique que l’opération de qubit simple est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="1fedd-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1fedd-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="1fedd-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="1fedd-108">singleElementOperation : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="1fedd-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1fedd-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="1fedd-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="1fedd-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="1fedd-110">register : 'T[]</span></span>

<span data-ttu-id="1fedd-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="1fedd-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1fedd-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1fedd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1fedd-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1fedd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1fedd-114">Peut</span><span class="sxs-lookup"><span data-stu-id="1fedd-114">'T</span></span>

<span data-ttu-id="1fedd-115">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="1fedd-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fedd-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1fedd-116">See Also</span></span>

- [<span data-ttu-id="1fedd-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="1fedd-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)