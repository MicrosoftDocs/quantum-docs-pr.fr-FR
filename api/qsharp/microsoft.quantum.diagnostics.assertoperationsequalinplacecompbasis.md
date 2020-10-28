---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: Opération AssertOperationsEqualInPlaceCompBasis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702751"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="7c2bd-102">Opération AssertOperationsEqualInPlaceCompBasis</span><span class="sxs-lookup"><span data-stu-id="7c2bd-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="7c2bd-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7c2bd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7c2bd-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c2bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c2bd-105">Vérifie si l’opération `givenU` est égale à l’opération `expectedU` sur la taille d’entrée donnée en vérifiant l’action des opérations uniquement sur les vecteurs à partir de la base de calcul.</span><span class="sxs-lookup"><span data-stu-id="7c2bd-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="7c2bd-106">Il s’agit d’une condition nécessaire, mais pas suffisante, pour l’égalité de deux unités.</span><span class="sxs-lookup"><span data-stu-id="7c2bd-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="7c2bd-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="7c2bd-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="7c2bd-108">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7c2bd-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7c2bd-109">Nombre de qubits $n $ que les opérations `givenU` et `expectedU` utilisent.</span><span class="sxs-lookup"><span data-stu-id="7c2bd-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="7c2bd-110">donné : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unité](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7c2bd-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7c2bd-111">Opération sur $n $ qubits à vérifier.</span><span class="sxs-lookup"><span data-stu-id="7c2bd-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="7c2bd-112">expected : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c2bd-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7c2bd-113">Opération de référence sur $n $ qubits `givenU` à comparer.</span><span class="sxs-lookup"><span data-stu-id="7c2bd-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c2bd-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c2bd-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

