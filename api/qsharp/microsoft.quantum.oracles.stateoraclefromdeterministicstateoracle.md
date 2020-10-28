---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708744"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="c1e04-102">StateOracleFromDeterministicStateOracle fonction)</span><span class="sxs-lookup"><span data-stu-id="c1e04-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="c1e04-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c1e04-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c1e04-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1e04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1e04-105">Convertit un Oracle de type `DeterministicStateOracle` en `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="c1e04-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="c1e04-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c1e04-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="c1e04-107">deterministicStateOracle : [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="c1e04-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="c1e04-108">Une préparation de l’État Oracle $A $ de type `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="c1e04-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="c1e04-109">Sortie : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="c1e04-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="c1e04-110">La même préparation d’État Oracle $A $, mais maintenant de type `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="c1e04-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="c1e04-111">Notez que l’index d’indicateur dans ce `StateOracle` est une variable factice et n’a aucun effet.</span><span class="sxs-lookup"><span data-stu-id="c1e04-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1e04-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1e04-112">See Also</span></span>

- [<span data-ttu-id="c1e04-113">Microsoft. Quantum. oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="c1e04-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="c1e04-114">Microsoft. Quantum. oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="c1e04-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)