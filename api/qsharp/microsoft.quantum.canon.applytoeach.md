---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Opération ApplyToEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844625"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="eecbc-102">Opération ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="eecbc-102">ApplyToEach operation</span></span>

<span data-ttu-id="eecbc-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eecbc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eecbc-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eecbc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eecbc-105">Applique une opération à qubit unique à chaque élément d’un registre.</span><span class="sxs-lookup"><span data-stu-id="eecbc-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="eecbc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="eecbc-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="eecbc-107">singleElementOperation : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eecbc-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="eecbc-108">Opération à appliquer à chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="eecbc-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="eecbc-109">inscrire : 't []</span><span class="sxs-lookup"><span data-stu-id="eecbc-109">register : 'T[]</span></span>

<span data-ttu-id="eecbc-110">Tableau de qubits sur lequel appliquer l’opération donnée.</span><span class="sxs-lookup"><span data-stu-id="eecbc-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eecbc-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eecbc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eecbc-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="eecbc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eecbc-113">Peut</span><span class="sxs-lookup"><span data-stu-id="eecbc-113">'T</span></span>

<span data-ttu-id="eecbc-114">Cible sur laquelle l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="eecbc-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="eecbc-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="eecbc-115">Example</span></span>

<span data-ttu-id="eecbc-116">Préparez un état de trois-qubit $ \ket{+} $ :</span><span class="sxs-lookup"><span data-stu-id="eecbc-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="eecbc-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eecbc-117">See Also</span></span>

- [<span data-ttu-id="eecbc-118">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="eecbc-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="eecbc-119">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="eecbc-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="eecbc-120">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="eecbc-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)