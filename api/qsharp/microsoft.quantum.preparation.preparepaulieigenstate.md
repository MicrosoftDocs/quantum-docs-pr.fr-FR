---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Opération PreparePauliEigenstate
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193690"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="7d4aa-102">Opération PreparePauliEigenstate</span><span class="sxs-lookup"><span data-stu-id="7d4aa-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="7d4aa-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7d4aa-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7d4aa-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d4aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d4aa-105">Prépare un qubit dans le eigenstate positif d’un opérateur Pauli donné.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="7d4aa-106">Si l’opérateur d’identité est donné, le qubit est préparé dans l’état de la même façon.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="7d4aa-107">Description</span><span class="sxs-lookup"><span data-stu-id="7d4aa-107">Description</span></span>

<span data-ttu-id="7d4aa-108">Si le qubit a été initialement dans l’État $ \ket {0} $, cette opération prépare le qubit dans le eigenstate $ + $1 d’un opérateur Pauli donné, ou, pour `PauliI` , dans l’état le plus maximal mélangé à la place (consultez <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="7d4aa-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="7d4aa-109">Si le qubit était dans un État autre que $ \ket {0} $, cette opération applique les portes suivantes : $H $ pour `PauliX` , $HS $ pour `PauliY` , $I $ pour `PauliZ` et <xref:microsoft.quantum.preparation.preparesinglequbitidentity> pour `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="7d4aa-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="7d4aa-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="7d4aa-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="7d4aa-111">base : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="7d4aa-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="7d4aa-112">Un opérateur Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="7d4aa-113">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d4aa-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d4aa-114">Qubit à préparer.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d4aa-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d4aa-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
