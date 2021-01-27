---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Opération ApplyXorInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843475"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="a7ff8-102">Opération ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="a7ff8-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="a7ff8-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a7ff8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a7ff8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7ff8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7ff8-105">Applique une opération XOR au niveau du bit entre un entier classique et un entier représenté par un registre de qubits.</span><span class="sxs-lookup"><span data-stu-id="a7ff8-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a7ff8-106">Description</span><span class="sxs-lookup"><span data-stu-id="a7ff8-106">Description</span></span>

<span data-ttu-id="a7ff8-107">Applique des `X` opérations à qubits dans un registre Little endian basé sur 1 bits dans un entier.</span><span class="sxs-lookup"><span data-stu-id="a7ff8-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="a7ff8-108">Faites-nous part `value` d’un et laissez y être un entier non signé encodé dans `target` , puis `InPlaceXorLE` effectue une opération donnée par le mappage suivant : $ \ket{y}\rightarrow \ket{y\oplus a} $, où $ \oplus $ est l’opérateur de bits or exclusif.</span><span class="sxs-lookup"><span data-stu-id="a7ff8-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="a7ff8-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="a7ff8-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="a7ff8-110">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a7ff8-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a7ff8-111">Entier qui est supposé être non négatif.</span><span class="sxs-lookup"><span data-stu-id="a7ff8-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="a7ff8-112">cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a7ff8-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a7ff8-113">Registre quantique utilisé pour stocker `value` l’encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="a7ff8-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7ff8-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7ff8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

