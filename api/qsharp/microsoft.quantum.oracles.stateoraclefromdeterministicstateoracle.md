---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: f3c225ee185b4b70ab0ea60af6f0fb154288d9bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193809"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>StateOracleFromDeterministicStateOracle fonction)

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convertit un Oracle de type `DeterministicStateOracle` en `StateOracle` .

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a>Entrée

### <a name="deterministicstateoracle--deterministicstateoracle"></a>deterministicStateOracle : [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Une préparation de l’État Oracle $A $ de type `DeterministicStateOracle` .



## <a name="output--stateoracle"></a>Sortie : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

La même préparation d’État Oracle $A $, mais maintenant de type `StateOracle` . Notez que l’index d’indicateur dans ce `StateOracle` est une variable factice et n’a aucun effet.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)