---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Opération MultiplyAndAddPhaseByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706398"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="1f821-102">Opération MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="1f821-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="1f821-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1f821-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1f821-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f821-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f821-105">Identique à MultiplyAndAddByModularInteger, mais suppose que opérande encode des entiers dans la base QFT.</span><span class="sxs-lookup"><span data-stu-id="1f821-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="1f821-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1f821-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="1f821-107">constMultiplier : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f821-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f821-108">Entier $a $ à ajouter à chaque étiquette d’état de base.</span><span class="sxs-lookup"><span data-stu-id="1f821-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="1f821-109">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f821-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f821-110">Le modulo $N $, que l’addition et la multiplication sont prises en ce qui concerne.</span><span class="sxs-lookup"><span data-stu-id="1f821-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="1f821-111">multiplicateur : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1f821-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1f821-112">Registre quantique qui représente un entier non signé dont la valeur doit être ajoutée à chaque étiquette d’état de base de `summand` .</span><span class="sxs-lookup"><span data-stu-id="1f821-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="1f821-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1f821-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="1f821-114">Registre quantique qui représente un entier non signé à utiliser comme cible pour cette opération.</span><span class="sxs-lookup"><span data-stu-id="1f821-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f821-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f821-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1f821-116">Notes</span><span class="sxs-lookup"><span data-stu-id="1f821-116">Remarks</span></span>

<span data-ttu-id="1f821-117">Suppose que `phaseSummand` a le bit le plus élevé défini sur 0.</span><span class="sxs-lookup"><span data-stu-id="1f821-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="1f821-118">Suppose également que la valeur de `phaseSummand` est inférieure à $N $.</span><span class="sxs-lookup"><span data-stu-id="1f821-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f821-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f821-119">See Also</span></span>

- [<span data-ttu-id="1f821-120">Microsoft. Quantum. Arithmetic. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="1f821-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)