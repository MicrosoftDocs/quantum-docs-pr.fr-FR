---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702925"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="cb71f-102">PauliArrayAsInt fonction)</span><span class="sxs-lookup"><span data-stu-id="cb71f-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="cb71f-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="cb71f-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="cb71f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb71f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb71f-105">Encode un opérateur Pauli à plusieurs qubit représenté sous la forme d’un tableau d’opérateurs Pauli qubit uniques en un entier.</span><span class="sxs-lookup"><span data-stu-id="cb71f-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="cb71f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="cb71f-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="cb71f-107">Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="cb71f-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="cb71f-108">Tableau d’au plus 31 opérateurs Pauli à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="cb71f-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="cb71f-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cb71f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cb71f-110">Entier qui identifie de manière unique `paulis` , comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="cb71f-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb71f-111">Notes</span><span class="sxs-lookup"><span data-stu-id="cb71f-111">Remarks</span></span>

<span data-ttu-id="cb71f-112">Chaque opérateur Pauli peut être encodé à l’aide de deux bits : $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="cb71f-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="cb71f-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="cb71f-113">\end{align} $$</span></span>

<span data-ttu-id="cb71f-114">À partir d’un tableau d’opérateurs Pauli `[P0, ..., Pn]` , cette fonction retourne un entier avec une expansion binaire formée en concaténant les mappages de chaque opérateur Pauli dans l’ordre Big-endian `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="cb71f-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>