---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: opération de _assertEqualOnBasisVector
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702832"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="dcf4a-102">opération de _assertEqualOnBasisVector</span><span class="sxs-lookup"><span data-stu-id="dcf4a-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="dcf4a-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="dcf4a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="dcf4a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dcf4a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dcf4a-105">Vérifie si le résultat de l’application de deux opérations `givenU` et `expectedU` à un état de base est le même.</span><span class="sxs-lookup"><span data-stu-id="dcf4a-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="dcf4a-106">L’état de base est décrit par le `basis` paramètre.</span><span class="sxs-lookup"><span data-stu-id="dcf4a-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="dcf4a-107"><xref:microsoft.quantum.extensions.fliptobasis>Pour plus d’informations sur cette description, consultez fonction.</span><span class="sxs-lookup"><span data-stu-id="dcf4a-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="dcf4a-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="dcf4a-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="dcf4a-109">base : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dcf4a-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="dcf4a-110">État de base spécifié par un ID d’état de base à qubit unique (0 <= ID <= 3) pour chaque $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="dcf4a-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="dcf4a-111">donné : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unité](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="dcf4a-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="dcf4a-112">Opération sur $n $ qubits à vérifier.</span><span class="sxs-lookup"><span data-stu-id="dcf4a-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="dcf4a-113">expected : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dcf4a-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="dcf4a-114">Opération de référence sur $n $ qubits à laquelle l’donnée doit être comparée.</span><span class="sxs-lookup"><span data-stu-id="dcf4a-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dcf4a-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dcf4a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

