---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Opération RippleCarryAdderD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: c4466feebb8ff6afcdcb5bf385ec10e807c00537
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706254"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="b11a6-102">Opération RippleCarryAdderD</span><span class="sxs-lookup"><span data-stu-id="b11a6-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="b11a6-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b11a6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b11a6-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b11a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b11a6-105">Les ondulations réversibles, sur place, ajoutent deux entiers.</span><span class="sxs-lookup"><span data-stu-id="b11a6-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="b11a6-106">Étant donné deux entiers $n $ bits encodés dans LittleEndian Registers `xs` et `ys` , et un qubit Carry, l’opération calcule la somme des deux entiers où les bits les plus significatifs du $n sont conservés `ys` et le bit d’exécution est XOR au qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="b11a6-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b11a6-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="b11a6-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="b11a6-108">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b11a6-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b11a6-109">LittleEndian qubit Register Encoding the First entier opérande.</span><span class="sxs-lookup"><span data-stu-id="b11a6-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="b11a6-110">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b11a6-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b11a6-111">LittleEndian qubit Register Encoding the second opérande entier, est modifié pour contenir le $n les bits les moins significatifs de la somme.</span><span class="sxs-lookup"><span data-stu-id="b11a6-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="b11a6-112">transporter : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b11a6-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b11a6-113">Transporter qubit, est XOR avec le bit le plus significatif de la somme.</span><span class="sxs-lookup"><span data-stu-id="b11a6-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b11a6-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b11a6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b11a6-115">Notes</span><span class="sxs-lookup"><span data-stu-id="b11a6-115">Remarks</span></span>

<span data-ttu-id="b11a6-116">L’opération contrôlée spécifiée utilise la symétrie et l’annulation mutuelle des opérations pour améliorer l’implémentation par défaut qui ajoute un contrôle à chaque opération.</span><span class="sxs-lookup"><span data-stu-id="b11a6-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="b11a6-117">Références</span><span class="sxs-lookup"><span data-stu-id="b11a6-117">References</span></span>

- <span data-ttu-id="b11a6-118">Thomas G. Draper : « addition sur un ordinateur quantique », 2000.</span><span class="sxs-lookup"><span data-stu-id="b11a6-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033