---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Opération ApplyToEachC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850851"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="6a345-102">Opération ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="6a345-102">ApplyToEachC operation</span></span>

<span data-ttu-id="6a345-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a345-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a345-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a345-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a345-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="6a345-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="6a345-106">Le modificateur `C` indique que l’opération de qubit simple est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="6a345-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="6a345-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="6a345-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="6a345-108">singleElementOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="6a345-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6a345-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="6a345-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="6a345-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="6a345-110">register : 'T[]</span></span>

<span data-ttu-id="6a345-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="6a345-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a345-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a345-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6a345-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6a345-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a345-114">Peut</span><span class="sxs-lookup"><span data-stu-id="6a345-114">'T</span></span>

<span data-ttu-id="6a345-115">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="6a345-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="6a345-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="6a345-116">Example</span></span>

<span data-ttu-id="6a345-117">Préparez un état de trois-qubit $ \ket{+} $ :</span><span class="sxs-lookup"><span data-stu-id="6a345-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="6a345-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6a345-118">See Also</span></span>

- [<span data-ttu-id="6a345-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="6a345-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)