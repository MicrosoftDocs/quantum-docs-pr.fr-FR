---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Type défini par l’utilisateur ObliviousOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 7c5b35984f3c8828a5ba9bdae8f9effbc1d378f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701905"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="6e01b-102">Type défini par l’utilisateur ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="6e01b-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="6e01b-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="6e01b-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="6e01b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e01b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e01b-105">Représente une amplification d’amplitude Oracle for oublie.</span><span class="sxs-lookup"><span data-stu-id="6e01b-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="6e01b-106">Les entrées de la $O Oracle sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="6e01b-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="6e01b-107">Le registre Ancilla $a $ sur lequel $O $ agit.</span><span class="sxs-lookup"><span data-stu-id="6e01b-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="6e01b-108">Le Registre du système $s $ sur lequel le $U unitaire souhaité est appliqué, après sélection du registre $a $ étant dans l’État $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="6e01b-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="6e01b-109">Notes</span><span class="sxs-lookup"><span data-stu-id="6e01b-109">Remarks</span></span>

<span data-ttu-id="6e01b-110">Ce Oracle défini par $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \Lambda\ket{t} \_ a U \ket{\Psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ agit sur l’État Ancilla $ \ket{s} \_ a $ pour implémenter le $U unitaire $ sur tout état du système $ \ket{\Psi} \_ s $ avec l’amplitude $ \lambda $ dans la base marquée par $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="6e01b-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="6e01b-111">Le premier paramètre est le registre qubit de $ \ket{s} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="6e01b-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="6e01b-112">Le deuxième paramètre est le registre qubit de $ \ket{\Psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="6e01b-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>