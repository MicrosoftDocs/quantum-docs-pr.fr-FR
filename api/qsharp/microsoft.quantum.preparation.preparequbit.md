---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Opération PrepareQubit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 84674d70d6a038ceaf1c637b22afa1b724d90795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193520"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="9c343-102">Opération PrepareQubit</span><span class="sxs-lookup"><span data-stu-id="9c343-102">PrepareQubit operation</span></span>

<span data-ttu-id="9c343-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9c343-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9c343-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c343-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="9c343-105">PrepareQubit est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="9c343-105">PrepareQubit has been deprecated.</span></span> <span data-ttu-id="9c343-106">Utilisez plutôt <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate>.</span><span class="sxs-lookup"><span data-stu-id="9c343-106">Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.</span></span>

<span data-ttu-id="9c343-107">Prépare un qubit dans le eigenstate + 1 ( `Zero` ) de l’opérateur Pauli donné.</span><span class="sxs-lookup"><span data-stu-id="9c343-107">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="9c343-108">Si l’opérateur d’identité est donné, le qubit est préparé dans l’état de la même façon.</span><span class="sxs-lookup"><span data-stu-id="9c343-108">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="9c343-109">Si le qubit a été initialement dans l’État $ \ket {0} $, cette opération prépare le qubit dans le eigenstate $ + $1 d’un opérateur Pauli donné, ou, pour `PauliI` , dans l’état le plus maximal mélangé à la place (consultez <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="9c343-109">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="9c343-110">Si le qubit était dans un État autre que $ \ket {0} $, cette opération applique les portes suivantes : $H $ pour `PauliX` , $HS $ pour `PauliY` , $I $ pour `PauliZ` et <xref:microsoft.quantum.preparation.preparesinglequbitidentity> pour `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="9c343-110">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9c343-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="9c343-111">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="9c343-112">base : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9c343-112">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9c343-113">Un opérateur Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="9c343-113">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="9c343-114">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9c343-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9c343-115">Qubit à préparer.</span><span class="sxs-lookup"><span data-stu-id="9c343-115">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c343-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c343-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

