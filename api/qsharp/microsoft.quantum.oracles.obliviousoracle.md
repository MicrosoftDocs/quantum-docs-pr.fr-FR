---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Type défini par l’utilisateur ObliviousOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842563"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="bdba3-102">Type défini par l’utilisateur ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="bdba3-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="bdba3-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="bdba3-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="bdba3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bdba3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bdba3-105">Représente une amplification d’amplitude Oracle for oublie.</span><span class="sxs-lookup"><span data-stu-id="bdba3-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="bdba3-106">Les entrées de la $O Oracle sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="bdba3-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="bdba3-107">Le registre Ancilla $a $ sur lequel $O $ agit.</span><span class="sxs-lookup"><span data-stu-id="bdba3-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="bdba3-108">Le Registre du système $s $ sur lequel le $U unitaire souhaité est appliqué, après sélection du registre $a $ étant dans l’État $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="bdba3-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="bdba3-109">Notes</span><span class="sxs-lookup"><span data-stu-id="bdba3-109">Remarks</span></span>

<span data-ttu-id="bdba3-110">Ce Oracle défini par $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \Lambda\ket{t} \_ a U \ket{\Psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ agit sur l’État Ancilla $ \ket{s} \_ a $ pour implémenter le $U unitaire $ sur tout état du système $ \ket{\Psi} \_ s $ avec l’amplitude $ \lambda $ dans la base marquée par $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="bdba3-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="bdba3-111">Le premier paramètre est le registre qubit de $ \ket{s} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="bdba3-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="bdba3-112">Le deuxième paramètre est le registre qubit de $ \ket{\Psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="bdba3-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>