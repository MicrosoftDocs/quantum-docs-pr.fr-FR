---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Type défini par l’utilisateur DeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193928"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="a39d8-102">Type défini par l’utilisateur DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="a39d8-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="a39d8-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a39d8-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a39d8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a39d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a39d8-105">Représente une préparation d’État Oracle for déterministe.</span><span class="sxs-lookup"><span data-stu-id="a39d8-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="a39d8-106">L’entrée dans le $O Oracle est :</span><span class="sxs-lookup"><span data-stu-id="a39d8-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="a39d8-107">Registre qui stocke l’État Quantum souhaité $ \ket{\Psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="a39d8-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="a39d8-108">Notes</span><span class="sxs-lookup"><span data-stu-id="a39d8-108">Remarks</span></span>

<span data-ttu-id="a39d8-109">Cette Oracle définie par $O \ket {0} = \ket{\Psi} $ agit sur l’état de base sur le calcul $ \ket {0} $ pour créer l’État $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="a39d8-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="a39d8-110">Le premier paramètre est le registre qubit de $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="a39d8-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>