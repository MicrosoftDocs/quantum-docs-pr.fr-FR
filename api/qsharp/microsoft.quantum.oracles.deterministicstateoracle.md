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
# <a name="deterministicstateoracle-user-defined-type"></a>Type défini par l’utilisateur DeterministicStateOracle

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une préparation d’État Oracle for déterministe.

L’entrée dans le $O Oracle est :

- Registre qui stocke l’État Quantum souhaité $ \ket{\Psi} \_ s $.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Notes

Cette Oracle définie par $O \ket {0} = \ket{\Psi} $ agit sur l’état de base sur le calcul $ \ket {0} $ pour créer l’État $ \ket{\Psi} $.
Le premier paramètre est le registre qubit de $ \ket{\Psi} $.