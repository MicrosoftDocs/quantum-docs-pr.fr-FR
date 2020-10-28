---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: Opération RippleCarryAdderTTK
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 5366ace36e63d361a439bfc5a1a78fdf9a353062
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706238"
---
# <a name="ripplecarryadderttk-operation"></a><span data-ttu-id="9bc20-102">Opération RippleCarryAdderTTK</span><span class="sxs-lookup"><span data-stu-id="9bc20-102">RippleCarryAdderTTK operation</span></span>

<span data-ttu-id="9bc20-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9bc20-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9bc20-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9bc20-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9bc20-105">Les ondulations réversibles, sur place, ajoutent deux entiers.</span><span class="sxs-lookup"><span data-stu-id="9bc20-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="9bc20-106">Étant donné deux entiers $n $ bits encodés dans LittleEndian Registers `xs` et `ys` , et un qubit Carry, l’opération calcule la somme des deux entiers où les bits les plus significatifs du $n sont conservés `ys` et le bit d’exécution est XOR au qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="9bc20-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9bc20-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="9bc20-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="9bc20-108">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9bc20-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9bc20-109">LittleEndian qubit Register Encoding the First entier opérande.</span><span class="sxs-lookup"><span data-stu-id="9bc20-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="9bc20-110">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9bc20-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9bc20-111">LittleEndian qubit Register Encoding the second opérande entier, est modifié pour contenir le $n les bits les moins significatifs de la somme.</span><span class="sxs-lookup"><span data-stu-id="9bc20-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="9bc20-112">transporter : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9bc20-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9bc20-113">Transporter qubit, est XOR avec le bit le plus significatif de la somme.</span><span class="sxs-lookup"><span data-stu-id="9bc20-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9bc20-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9bc20-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9bc20-115">Notes</span><span class="sxs-lookup"><span data-stu-id="9bc20-115">Remarks</span></span>

<span data-ttu-id="9bc20-116">Cette opération a les mêmes fonctionnalités que RippleCarryAdderD et, RippleCarryAdderCDKM, mais n’utilise aucune qubits Ancilla.</span><span class="sxs-lookup"><span data-stu-id="9bc20-116">This operation has the same functionality as RippleCarryAdderD and, RippleCarryAdderCDKM but does not use any ancilla qubits.</span></span>

## <a name="references"></a><span data-ttu-id="9bc20-117">Références</span><span class="sxs-lookup"><span data-stu-id="9bc20-117">References</span></span>

- <span data-ttu-id="9bc20-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro : « circuits d’addition quantiques et sortants non liés », informations de Quantum et calcul, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="9bc20-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530