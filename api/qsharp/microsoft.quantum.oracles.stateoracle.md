---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Type défini par l’utilisateur StateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854465"
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