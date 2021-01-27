---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: opération de _assertEqualOnBasisVector
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853579"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="59c03-102">opération de _assertEqualOnBasisVector</span><span class="sxs-lookup"><span data-stu-id="59c03-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="59c03-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="59c03-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="59c03-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="59c03-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="59c03-105">Vérifie si le résultat de l’application de deux opérations `givenU` et `expectedU` à un état de base est le même.</span><span class="sxs-lookup"><span data-stu-id="59c03-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="59c03-106">L’état de base est décrit par le `basis` paramètre.</span><span class="sxs-lookup"><span data-stu-id="59c03-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="59c03-107"><xref:microsoft.quantum.extensions.fliptobasis>Pour plus d’informations sur cette description, consultez fonction.</span><span class="sxs-lookup"><span data-stu-id="59c03-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="59c03-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="59c03-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="59c03-109">base : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="59c03-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="59c03-110">État de base spécifié par un ID d’état de base à qubit unique (0 <= ID <= 3) pour chaque $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="59c03-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="59c03-111">donné : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unité](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="59c03-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="59c03-112">Opération sur $n $ qubits à vérifier.</span><span class="sxs-lookup"><span data-stu-id="59c03-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="59c03-113">expected : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="59c03-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="59c03-114">Opération de référence sur $n $ qubits à laquelle l’donnée doit être comparée.</span><span class="sxs-lookup"><span data-stu-id="59c03-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59c03-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59c03-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

