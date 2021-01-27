---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Type défini par l’utilisateur DeterministicStateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842590"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="00b75-102">Type défini par l’utilisateur DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="00b75-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="00b75-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="00b75-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="00b75-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00b75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00b75-105">Représente une préparation d’État Oracle for déterministe.</span><span class="sxs-lookup"><span data-stu-id="00b75-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="00b75-106">L’entrée dans le $O Oracle est :</span><span class="sxs-lookup"><span data-stu-id="00b75-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="00b75-107">Registre qui stocke l’État Quantum souhaité $ \ket{\Psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="00b75-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="00b75-108">Notes</span><span class="sxs-lookup"><span data-stu-id="00b75-108">Remarks</span></span>

<span data-ttu-id="00b75-109">Cette Oracle définie par $O \ket {0} = \ket{\Psi} $ agit sur l’état de base sur le calcul $ \ket {0} $ pour créer l’État $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="00b75-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="00b75-110">Le premier paramètre est le registre qubit de $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="00b75-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>