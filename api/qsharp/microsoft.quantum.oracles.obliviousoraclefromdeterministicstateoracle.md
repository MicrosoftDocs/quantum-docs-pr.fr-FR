---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707889"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="10731-102">ObliviousOracleFromDeterministicStateOracle fonction)</span><span class="sxs-lookup"><span data-stu-id="10731-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="10731-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="10731-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="10731-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10731-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10731-105">Combine les Oracle `DeterministicStateOracle` et `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="10731-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="10731-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="10731-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="10731-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="10731-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="10731-108">Une préparation d’État Oracle $A $ de type `DeterministicStateOracle` agissant sur le registre $a $.</span><span class="sxs-lookup"><span data-stu-id="10731-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="10731-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="10731-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="10731-110">Oracle $U $ de type `ObliviousOracle` agissant conjointement sur register $a, s $.</span><span class="sxs-lookup"><span data-stu-id="10731-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="10731-111">Sortie : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="10731-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="10731-112">Oracle $O = UA $ de type `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="10731-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="10731-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10731-113">See Also</span></span>

- [<span data-ttu-id="10731-114">Microsoft. Quantum. oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="10731-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="10731-115">Microsoft. Quantum. oracles. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="10731-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)