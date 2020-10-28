---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Opération PrepareQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708225"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="9d19a-102">Opération PrepareQubit</span><span class="sxs-lookup"><span data-stu-id="9d19a-102">PrepareQubit operation</span></span>

<span data-ttu-id="9d19a-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9d19a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9d19a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d19a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d19a-105">Prépare un qubit dans le eigenstate + 1 ( `Zero` ) de l’opérateur Pauli donné.</span><span class="sxs-lookup"><span data-stu-id="9d19a-105">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="9d19a-106">Si l’opérateur d’identité est donné, le qubit est préparé dans l’état de la même façon.</span><span class="sxs-lookup"><span data-stu-id="9d19a-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="9d19a-107">Si le qubit a été initialement dans l’État $ \ket {0} $, cette opération prépare le qubit dans le eigenstate $ + $1 d’un opérateur Pauli donné, ou, pour `PauliI` , dans l’état le plus maximal mélangé à la place (consultez <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="9d19a-107">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="9d19a-108">Si le qubit était dans un État autre que $ \ket {0} $, cette opération applique les portes suivantes : $H $ pour `PauliX` , $HS $ pour `PauliY` , $I $ pour `PauliZ` et <xref:microsoft.quantum.preparation.preparesinglequbitidentity> pour `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="9d19a-108">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9d19a-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="9d19a-109">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="9d19a-110">base : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9d19a-110">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9d19a-111">Un opérateur Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="9d19a-111">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="9d19a-112">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9d19a-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9d19a-113">Qubit à préparer.</span><span class="sxs-lookup"><span data-stu-id="9d19a-113">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d19a-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d19a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

