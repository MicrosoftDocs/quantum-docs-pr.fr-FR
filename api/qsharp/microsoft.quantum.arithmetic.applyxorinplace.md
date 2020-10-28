---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Opération ApplyXorInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707459"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="e643f-102">Opération ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="e643f-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="e643f-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e643f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e643f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e643f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e643f-105">Applique une opération XOR au niveau du bit entre un entier classique et un entier représenté par un registre de qubits.</span><span class="sxs-lookup"><span data-stu-id="e643f-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="e643f-106">Description</span><span class="sxs-lookup"><span data-stu-id="e643f-106">Description</span></span>

<span data-ttu-id="e643f-107">Applique des `X` opérations à qubits dans un registre Little endian basé sur 1 bits dans un entier.</span><span class="sxs-lookup"><span data-stu-id="e643f-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="e643f-108">Faites-nous part `value` d’un et laissez y être un entier non signé encodé dans `target` , puis `InPlaceXorLE` effectue une opération donnée par le mappage suivant : $ \ket{y}\rightarrow \ket{y\oplus a} $, où $ \oplus $ est l’opérateur de bits or exclusif.</span><span class="sxs-lookup"><span data-stu-id="e643f-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="e643f-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="e643f-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="e643f-110">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e643f-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e643f-111">Entier qui est supposé être non négatif.</span><span class="sxs-lookup"><span data-stu-id="e643f-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="e643f-112">cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e643f-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e643f-113">Registre quantique utilisé pour stocker `value` l’encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="e643f-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e643f-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e643f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

