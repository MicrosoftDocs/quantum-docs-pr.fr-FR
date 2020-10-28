---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707871"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="a30b2-102">ReflectionOracleFromDeterministicStateOracle fonction)</span><span class="sxs-lookup"><span data-stu-id="a30b2-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="a30b2-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a30b2-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a30b2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a30b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a30b2-105">Construit une réflexion sur un État donné à partir d’un Oracle.</span><span class="sxs-lookup"><span data-stu-id="a30b2-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="a30b2-106">Description</span><span class="sxs-lookup"><span data-stu-id="a30b2-106">Description</span></span>

<span data-ttu-id="a30b2-107">À partir d’une préparation d’État déterministe Oracle représentée par une matrice d’unités $O $, le résultat de cette fonction est un Oracle qui applique une réflexion autour de l’État $ \ket{\Psi} $ préparé par Oracle $O $; autrement dit, l’État $ \ket{\Psi} $ tel que $O \ket {0} = \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="a30b2-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="a30b2-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="a30b2-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="a30b2-109">Oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="a30b2-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="a30b2-110">Oracle qui prépare les copies de l’État $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="a30b2-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="a30b2-111">Sortie : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a30b2-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a30b2-112">Oracle qui reflète l’État $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="a30b2-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="a30b2-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a30b2-113">See Also</span></span>

- [<span data-ttu-id="a30b2-114">Microsoft. Quantum. oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="a30b2-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="a30b2-115">Microsoft. Quantum. oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="a30b2-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)