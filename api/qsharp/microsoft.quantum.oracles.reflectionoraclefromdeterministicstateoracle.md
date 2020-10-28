---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707871"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle fonction)

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Packages [](https://nuget.org/packages/)


Construit une réflexion sur un État donné à partir d’un Oracle.

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>Description

À partir d’une préparation d’État déterministe Oracle représentée par une matrice d’unités $O $, le résultat de cette fonction est un Oracle qui applique une réflexion autour de l’État $ \ket{\Psi} $ préparé par Oracle $O $; autrement dit, l’État $ \ket{\Psi} $ tel que $O \ket {0} = \ket{\Psi} $.

## <a name="input"></a>Entrée

### <a name="oracle--deterministicstateoracle"></a>Oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Oracle qui prépare les copies de l’État $ \ket{\Psi} $.



## <a name="output--reflectionoracle"></a>Sortie : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Oracle qui reflète l’État $ \ket{\Psi} $.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. oracles. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)