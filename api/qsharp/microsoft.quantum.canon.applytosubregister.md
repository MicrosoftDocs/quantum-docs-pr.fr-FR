---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Opération ApplyToSubregister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704662"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="a3e5f-102">Opération ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="a3e5f-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="a3e5f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a3e5f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a3e5f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3e5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3e5f-105">Applique une opération à un sous-registre d’un registre, avec qubits spécifié par un tableau de leurs index.</span><span class="sxs-lookup"><span data-stu-id="a3e5f-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a3e5f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a3e5f-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="a3e5f-107">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3e5f-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a3e5f-108">Opération à appliquer à subregister.</span><span class="sxs-lookup"><span data-stu-id="a3e5f-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="a3e5f-109">idxs : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a3e5f-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a3e5f-110">Tableau d’index, indiquant à quel qubits l’opération sera appliquée.</span><span class="sxs-lookup"><span data-stu-id="a3e5f-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a3e5f-111">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a3e5f-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a3e5f-112">Inscrivez-vous sur lequel l’opération agit.</span><span class="sxs-lookup"><span data-stu-id="a3e5f-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3e5f-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3e5f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a3e5f-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3e5f-114">See Also</span></span>

- [<span data-ttu-id="a3e5f-115">Microsoft. Quantum. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="a3e5f-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="a3e5f-116">Microsoft. Quantum. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="a3e5f-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="a3e5f-117">Microsoft. Quantum. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="a3e5f-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)