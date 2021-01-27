---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: Opération RippleCarryAdderNoCarryTTK
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 0e131204d3eaff7f99aa9ff7c3c1ae93a1bf611b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846342"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="21e9b-102">Opération RippleCarryAdderNoCarryTTK</span><span class="sxs-lookup"><span data-stu-id="21e9b-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="21e9b-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="21e9b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="21e9b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21e9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21e9b-105">Les ondulations réversibles, sur place, ajoutent deux entiers sans effectuer de réalisation.</span><span class="sxs-lookup"><span data-stu-id="21e9b-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="21e9b-106">Description</span><span class="sxs-lookup"><span data-stu-id="21e9b-106">Description</span></span>

<span data-ttu-id="21e9b-107">Étant donné deux entiers de $n $ bits encodés dans LittleEndian Registers `xs` et `ys` , l’opération calcule la somme des deux entiers modulo $2 ^ n $, où $n $ correspond à la taille en bits des entrées `xs` et `ys` .</span><span class="sxs-lookup"><span data-stu-id="21e9b-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="21e9b-108">Elle ne calcule pas le bit de réalisation.</span><span class="sxs-lookup"><span data-stu-id="21e9b-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="21e9b-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="21e9b-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="21e9b-110">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="21e9b-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="21e9b-111">LittleEndian qubit Register Encoding the First entier opérande.</span><span class="sxs-lookup"><span data-stu-id="21e9b-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="21e9b-112">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="21e9b-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="21e9b-113">LittleEndian qubit Register Encoding the second opérande entier, est modifié pour contenir le $n les bits les moins significatifs de la somme.</span><span class="sxs-lookup"><span data-stu-id="21e9b-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21e9b-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21e9b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="21e9b-115">Notes</span><span class="sxs-lookup"><span data-stu-id="21e9b-115">Remarks</span></span>

<span data-ttu-id="21e9b-116">Cette opération a la même fonctionnalité que RippleCarryAdderTTK, mais elle ne retourne pas le bit de transport.</span><span class="sxs-lookup"><span data-stu-id="21e9b-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="21e9b-117">Références</span><span class="sxs-lookup"><span data-stu-id="21e9b-117">References</span></span>

- <span data-ttu-id="21e9b-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro : « circuits d’addition quantiques et sortants non liés », informations de Quantum et calcul, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="21e9b-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530