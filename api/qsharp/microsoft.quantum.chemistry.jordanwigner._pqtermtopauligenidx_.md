---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 7f1794f9e46323ccf722407fb7ae82f73ed76e40
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215433"
---
# <a name="_pqtermtopauligenidx_-function"></a>_PQTermToPauliGenIdx_ fonction)

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Convertit un GeneratorIndex décrivant un terme PQ en une expression « GeneratorIndex [] » en termes de Paulis

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>Entrée

### <a name="term--generatorindex"></a>terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` représentant un terme PQ.



## <a name="output--generatorindex"></a>Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

« GeneratorIndex [] » exprimant le terme PQ en tant que termes Pauli.