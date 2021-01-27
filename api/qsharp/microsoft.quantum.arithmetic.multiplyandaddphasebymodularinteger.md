---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Opération MultiplyAndAddPhaseByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: b1214acc2cafc3fede9fcb6663a435c0b1d2cf4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843058"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="1c589-102">Opération MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="1c589-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="1c589-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1c589-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1c589-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c589-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1c589-105">Identique à MultiplyAndAddByModularInteger, mais suppose que opérande encode des entiers dans la base QFT.</span><span class="sxs-lookup"><span data-stu-id="1c589-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1c589-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1c589-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="1c589-107">constMultiplier : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c589-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c589-108">Entier $a $ à ajouter à chaque étiquette d’état de base.</span><span class="sxs-lookup"><span data-stu-id="1c589-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="1c589-109">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c589-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c589-110">Le modulo $N $, que l’addition et la multiplication sont prises en ce qui concerne.</span><span class="sxs-lookup"><span data-stu-id="1c589-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="1c589-111">multiplicateur : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1c589-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1c589-112">Registre quantique qui représente un entier non signé dont la valeur doit être ajoutée à chaque étiquette d’état de base de `summand` .</span><span class="sxs-lookup"><span data-stu-id="1c589-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="1c589-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1c589-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="1c589-114">Registre quantique qui représente un entier non signé à utiliser comme cible pour cette opération.</span><span class="sxs-lookup"><span data-stu-id="1c589-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c589-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c589-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1c589-116">Notes</span><span class="sxs-lookup"><span data-stu-id="1c589-116">Remarks</span></span>

<span data-ttu-id="1c589-117">Suppose que `phaseSummand` a le bit le plus élevé défini sur 0.</span><span class="sxs-lookup"><span data-stu-id="1c589-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="1c589-118">Suppose également que la valeur de `phaseSummand` est inférieure à $N $.</span><span class="sxs-lookup"><span data-stu-id="1c589-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c589-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c589-119">See Also</span></span>

- [<span data-ttu-id="1c589-120">Microsoft. Quantum. Arithmetic. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="1c589-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)