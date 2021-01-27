---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: 4eed29072cab9e8c106509a6a114c8a071441079
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842506"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="16cd5-102">StateOracleFromDeterministicStateOracle fonction)</span><span class="sxs-lookup"><span data-stu-id="16cd5-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="16cd5-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="16cd5-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="16cd5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16cd5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16cd5-105">Convertit un Oracle de type `DeterministicStateOracle` en `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="16cd5-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="16cd5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="16cd5-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="16cd5-107">deterministicStateOracle : [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="16cd5-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="16cd5-108">Une préparation de l’État Oracle $A $ de type `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="16cd5-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="16cd5-109">Sortie : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="16cd5-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="16cd5-110">La même préparation d’État Oracle $A $, mais maintenant de type `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="16cd5-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="16cd5-111">Notez que l’index d’indicateur dans ce `StateOracle` est une variable factice et n’a aucun effet.</span><span class="sxs-lookup"><span data-stu-id="16cd5-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="16cd5-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16cd5-112">See Also</span></span>

- [<span data-ttu-id="16cd5-113">Microsoft. Quantum. oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="16cd5-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="16cd5-114">Microsoft. Quantum. oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="16cd5-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)