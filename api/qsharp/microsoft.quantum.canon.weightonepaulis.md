---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703708"
---
# <a name="weightonepaulis-function"></a>WeightOnePaulis fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Retourne un tableau de tous les opérateurs Weight-1 Pauli sur un nombre donné de qubits.

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits sur lesquels les opérateurs Pauli retournés sont définis.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tableau d’opérateurs Pauli qubit, chacun d’eux étant représenté sous la forme d’un tableau de longueur `nQubits` .