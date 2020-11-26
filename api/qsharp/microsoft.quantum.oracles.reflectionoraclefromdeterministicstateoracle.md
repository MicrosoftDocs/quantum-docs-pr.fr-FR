---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: 09de63d615a4d80e2b59deeddc07567aefe7660e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193826"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="02457-102">ReflectionOracleFromDeterministicStateOracle fonction)</span><span class="sxs-lookup"><span data-stu-id="02457-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="02457-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="02457-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="02457-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02457-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02457-105">Construit une réflexion sur un État donné à partir d’un Oracle.</span><span class="sxs-lookup"><span data-stu-id="02457-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="02457-106">Description</span><span class="sxs-lookup"><span data-stu-id="02457-106">Description</span></span>

<span data-ttu-id="02457-107">À partir d’une préparation d’État déterministe Oracle représentée par une matrice d’unités $O $, le résultat de cette fonction est un Oracle qui applique une réflexion autour de l’État $ \ket{\Psi} $ préparé par Oracle $O $; autrement dit, l’État $ \ket{\Psi} $ tel que $O \ket {0} = \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="02457-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="02457-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="02457-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="02457-109">Oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="02457-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="02457-110">Oracle qui prépare les copies de l’État $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="02457-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="02457-111">Sortie : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="02457-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="02457-112">Oracle qui reflète l’État $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="02457-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="02457-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02457-113">See Also</span></span>

- [<span data-ttu-id="02457-114">Microsoft. Quantum. oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="02457-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="02457-115">Microsoft. Quantum. oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="02457-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)