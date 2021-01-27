---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Type défini par l’utilisateur DiscreteOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: 4b85f58889ef9cc55518009bdd9b59bdb2b5b842
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842568"
---
# <a name="discreteoracle-user-defined-type"></a>Type défini par l’utilisateur DiscreteOracle

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une Oracle discrète.

Il s’agit d’un Oracle qui implémente $U ^ m $ pour une opération fixe $U $ et un entier non négatif $m $.

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

