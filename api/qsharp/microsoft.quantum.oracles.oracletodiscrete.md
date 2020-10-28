---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708756"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete fonction)

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Packages [](https://nuget.org/packages/)


Dans le cas d’une opération qui représente une « boîte noire » Oracle, retourne une Oracle discrète qui représente la « boîte noire » Oracle répétée plusieurs fois.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Entrée

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a>blackBoxOracle : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL

Opération à élever.



## <a name="output--discreteoracle"></a>Sortie : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Opération partiellement appliquée sur la « boîte noire » Oracle représentant le temps d’Oracle discret