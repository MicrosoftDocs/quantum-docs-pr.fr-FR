---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Type défini par l’utilisateur StateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226602"
---
# <a name="stateoracle-user-defined-type"></a>Type défini par l’utilisateur StateOracle

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente un Oracle pour la préparation de l’État.

Les entrées de la $O Oracle sont les suivantes :

- Entier qui indexe l’indicateur qubit $f $.
- Le registre système $s $ qui stocke l’État Quantum souhaité $ \ket{\Psi} \_ s $.

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Notes

Cette Oracle définie par $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ agit sur l’état de base sur le calcul $ \ket {0} \_ {f} \ket {0} \_ s $ pour créer l’État cible $ \ket{\Psi} \_ s $ avec l’amplitude $ \lambda $ dans la base marquée par $ \ket {1} \_ f $.
Le premier paramètre est un index du Registre qubit de $ \ket {0} \_ f $. Le deuxième paramètre englobe les deux registres.