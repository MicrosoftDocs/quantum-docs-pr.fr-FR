---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Type défini par l’utilisateur DeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708777"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="db350-102">Type défini par l’utilisateur DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="db350-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="db350-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="db350-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="db350-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db350-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db350-105">Représente une préparation d’État Oracle for déterministe.</span><span class="sxs-lookup"><span data-stu-id="db350-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="db350-106">L’entrée dans le $O Oracle est :</span><span class="sxs-lookup"><span data-stu-id="db350-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="db350-107">Registre qui stocke l’État Quantum souhaité $ \ket{\Psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="db350-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="db350-108">Notes</span><span class="sxs-lookup"><span data-stu-id="db350-108">Remarks</span></span>

<span data-ttu-id="db350-109">Cette Oracle définie par $O \ket {0} = \ket{\Psi} $ agit sur l’état de base sur le calcul $ \ket {0} $ pour créer l’État $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="db350-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="db350-110">Le premier paramètre est le registre qubit de $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="db350-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>