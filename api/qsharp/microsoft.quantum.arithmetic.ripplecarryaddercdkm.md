---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Opération RippleCarryAdderCDKM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: 6dcb5193c5d1d059682a79e63e6562aabff7539d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706270"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="7615a-102">Opération RippleCarryAdderCDKM</span><span class="sxs-lookup"><span data-stu-id="7615a-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="7615a-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7615a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7615a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7615a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7615a-105">Les ondulations réversibles, sur place, ajoutent deux entiers.</span><span class="sxs-lookup"><span data-stu-id="7615a-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="7615a-106">Description</span><span class="sxs-lookup"><span data-stu-id="7615a-106">Description</span></span>

<span data-ttu-id="7615a-107">Étant donné deux entiers $n $ bits encodés dans LittleEndian Registers `xs` et `ys` , et un qubit Carry, l’opération calcule la somme des deux entiers où les bits les plus significatifs du $n sont conservés `ys` et le bit d’exécution est XOR au qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="7615a-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="7615a-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="7615a-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="7615a-109">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7615a-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7615a-110">LittleEndian qubit Register Encoding the First entier opérande.</span><span class="sxs-lookup"><span data-stu-id="7615a-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="7615a-111">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7615a-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7615a-112">LittleEndian qubit Register Encoding the second opérande entier, est modifié pour contenir les n bits les moins significatifs de la somme.</span><span class="sxs-lookup"><span data-stu-id="7615a-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="7615a-113">transporter : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7615a-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7615a-114">Transporter qubit, est XOR avec le bit le plus significatif de la somme.</span><span class="sxs-lookup"><span data-stu-id="7615a-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7615a-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7615a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7615a-116">Notes</span><span class="sxs-lookup"><span data-stu-id="7615a-116">Remarks</span></span>

<span data-ttu-id="7615a-117">Cette opération a la même fonctionnalité que RippleCarryAdderD, mais utilise uniquement un qubit auxiliaire au lieu de $n $.</span><span class="sxs-lookup"><span data-stu-id="7615a-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="7615a-118">Références</span><span class="sxs-lookup"><span data-stu-id="7615a-118">References</span></span>

- <span data-ttu-id="7615a-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton : « A New Quantum ondulation-Carry apporting circuit », 2004.</span><span class="sxs-lookup"><span data-stu-id="7615a-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1