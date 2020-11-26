---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: 09de63d615a4d80e2b59deeddc07567aefe7660e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193826"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle fonction)

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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