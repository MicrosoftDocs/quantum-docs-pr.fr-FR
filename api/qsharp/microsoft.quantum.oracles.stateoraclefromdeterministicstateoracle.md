---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708744"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>StateOracleFromDeterministicStateOracle fonction)

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Packages [](https://nuget.org/packages/)


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