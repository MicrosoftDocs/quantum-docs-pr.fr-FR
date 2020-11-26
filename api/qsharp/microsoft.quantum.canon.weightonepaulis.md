---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204536"
---
# <a name="weightonepaulis-function"></a>WeightOnePaulis fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne un tableau de tous les opérateurs Weight-1 Pauli sur un nombre donné de qubits.

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits sur lesquels les opérateurs Pauli retournés sont définis.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tableau d’opérateurs Pauli qubit, chacun d’eux étant représenté sous la forme d’un tableau de longueur `nQubits` .