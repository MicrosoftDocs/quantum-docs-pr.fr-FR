---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: Opération ApplyToEachA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844614"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="53caa-102">Opération ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="53caa-102">ApplyToEachA operation</span></span>

<span data-ttu-id="53caa-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="53caa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="53caa-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53caa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53caa-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="53caa-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="53caa-106">Le modificateur `A` indique que l’opération à qubit unique est adjointable.</span><span class="sxs-lookup"><span data-stu-id="53caa-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="53caa-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="53caa-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="53caa-108">singleElementOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="53caa-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="53caa-109">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="53caa-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="53caa-110">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="53caa-110">register : 'T[]</span></span>

<span data-ttu-id="53caa-111">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="53caa-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53caa-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53caa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="53caa-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="53caa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="53caa-114">Peut</span><span class="sxs-lookup"><span data-stu-id="53caa-114">'T</span></span>

<span data-ttu-id="53caa-115">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="53caa-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="53caa-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="53caa-116">Example</span></span>

<span data-ttu-id="53caa-117">Préparez un état de trois-qubit $ \ket{+} $ :</span><span class="sxs-lookup"><span data-stu-id="53caa-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="53caa-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53caa-118">See Also</span></span>

- [<span data-ttu-id="53caa-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="53caa-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)