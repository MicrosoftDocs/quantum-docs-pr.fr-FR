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
# <a name="obliviousoracle-user-defined-type"></a>Type défini par l’utilisateur ObliviousOracle

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une amplification d’amplitude Oracle for oublie.

Les entrées de la $O Oracle sont les suivantes :

- Le registre Ancilla $a $ sur lequel $O $ agit.
- Le Registre du système $s $ sur lequel le $U unitaire souhaité est appliqué, après sélection du registre $a $ étant dans l’État $ \ket{t} \_ a $.

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Notes

Ce Oracle défini par $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \Lambda\ket{t} \_ a U \ket{\Psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ agit sur l’État Ancilla $ \ket{s} \_ a $ pour implémenter le $U unitaire $ sur tout état du système $ \ket{\Psi} \_ s $ avec l’amplitude $ \lambda $ dans la base marquée par $ \ket{t} \_ a $.
Le premier paramètre est le registre qubit de $ \ket{s} \_ a $. Le deuxième paramètre est le registre qubit de $ \ket{\Psi} \_ s $.