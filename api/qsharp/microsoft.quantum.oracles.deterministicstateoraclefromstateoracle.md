---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708759"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle fonction)

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Packages [](https://nuget.org/packages/)


Convertit un Oracle de type `StateOracle` en `DeterministicStateOracle` .

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a>Entrée

### <a name="idxflagqubit--int"></a>idxFlagQubit : [entier](xref:microsoft.quantum.lang-ref.int)

L’index de l’indicateur qubit de l' `stateOracle` $A $, qui agit explicitement sur deux registres : l’indicateur $f $ et le système $s $, par exemple $A \ket {0} \_ f\ket {\ PSI} \_ s $.


### <a name="stateoracle--stateoracle"></a>stateOracle : [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Une préparation de l’État Oracle $A $ de type `StateOracle` .



## <a name="output--deterministicstateoracle"></a>Sortie : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

La même préparation d’État Oracle $A $, mais maintenant de type `DeterministicStateOracle` , elle agit donc sur un registre où $a, s $ n’est plus explicitement séparé, par exemple  $A \ket{0\psi} \_ {As} $.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)
- [Microsoft. Quantum. oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)