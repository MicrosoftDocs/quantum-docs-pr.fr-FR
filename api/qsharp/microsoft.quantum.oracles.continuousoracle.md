---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Type défini par l’utilisateur ContinuousOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: fb05e97c635ba75fc2d85dc2a7cea27f3a3af63f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226789"
---
# <a name="continuousoracle-user-defined-type"></a>Type défini par l’utilisateur ContinuousOracle

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une Oracle à temps continu.

Il s’agit d’un Oracle qui implémente $U (\delta t) : \ket{\Psi (t)} \mapsto \ket{\Psi (t + \delta t)} $ pour toutes les heures $t $, où $U $ est une opération fixe et où $ \delta t $ est un nombre réel non négatif.

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

