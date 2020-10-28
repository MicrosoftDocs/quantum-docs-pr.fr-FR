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
# <a name="deterministicstateoracle-user-defined-type"></a>Type défini par l’utilisateur DeterministicStateOracle

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Packages [](https://nuget.org/packages/)


Représente une préparation d’État Oracle for déterministe.

L’entrée dans le $O Oracle est :

- Registre qui stocke l’État Quantum souhaité $ \ket{\Psi} \_ s $.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Notes

Cette Oracle définie par $O \ket {0} = \ket{\Psi} $ agit sur l’état de base sur le calcul $ \ket {0} $ pour créer l’État $ \ket{\Psi} $.
Le premier paramètre est le registre qubit de $ \ket{\Psi} $.