---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Type défini par l’utilisateur StateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708747"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="3b2d0-102">Type défini par l’utilisateur StateOracle</span><span class="sxs-lookup"><span data-stu-id="3b2d0-102">StateOracle user defined type</span></span>

<span data-ttu-id="3b2d0-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="3b2d0-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="3b2d0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b2d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b2d0-105">Représente un Oracle pour la préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="3b2d0-106">Les entrées de la $O Oracle sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3b2d0-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="3b2d0-107">Entier qui indexe l’indicateur qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="3b2d0-108">Le registre système $s $ qui stocke l’État Quantum souhaité $ \ket{\Psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="3b2d0-109">Notes</span><span class="sxs-lookup"><span data-stu-id="3b2d0-109">Remarks</span></span>

<span data-ttu-id="3b2d0-110">Cette Oracle définie par $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ agit sur l’état de base sur le calcul $ \ket {0} \_ {f} \ket {0} \_ s $ pour créer l’État cible $ \ket{\Psi} \_ s $ avec l’amplitude $ \lambda $ dans la base marquée par $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="3b2d0-111">Le premier paramètre est un index du Registre qubit de $ \ket {0} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="3b2d0-112">Le deuxième paramètre englobe les deux registres.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-112">The second parameter encompassed both registers.</span></span>