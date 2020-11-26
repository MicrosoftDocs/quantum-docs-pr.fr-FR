---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193843"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete fonction)

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dans le cas d’une opération qui représente une « boîte noire » Oracle, retourne une Oracle discrète qui représente la « boîte noire » Oracle répétée plusieurs fois.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Entrée

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>blackBoxOracle : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération à élever.



## <a name="output--discreteoracle"></a>Sortie : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Opération partiellement appliquée sur la « boîte noire » Oracle représentant le temps d’Oracle discret