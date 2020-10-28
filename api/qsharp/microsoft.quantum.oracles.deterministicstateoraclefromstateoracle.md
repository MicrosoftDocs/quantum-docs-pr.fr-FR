---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708759"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="6011f-102">DeterministicStateOracleFromStateOracle fonction)</span><span class="sxs-lookup"><span data-stu-id="6011f-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="6011f-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="6011f-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="6011f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6011f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6011f-105">Convertit un Oracle de type `StateOracle` en `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="6011f-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="6011f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6011f-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="6011f-107">idxFlagQubit : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6011f-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6011f-108">L’index de l’indicateur qubit de l' `stateOracle` $A $, qui agit explicitement sur deux registres : l’indicateur $f $ et le système $s $, par exemple $A \ket {0} \_ f\ket {\ PSI} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="6011f-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="6011f-109">stateOracle : [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="6011f-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="6011f-110">Une préparation de l’État Oracle $A $ de type `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="6011f-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="6011f-111">Sortie : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="6011f-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="6011f-112">La même préparation d’État Oracle $A $, mais maintenant de type `DeterministicStateOracle` , elle agit donc sur un registre où $a, s $ n’est plus explicitement séparé, par exemple  $A \ket{0\psi} \_ {As} $.</span><span class="sxs-lookup"><span data-stu-id="6011f-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="6011f-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6011f-113">See Also</span></span>

- [<span data-ttu-id="6011f-114">Microsoft. Quantum. oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="6011f-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="6011f-115">Microsoft. Quantum. oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="6011f-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)