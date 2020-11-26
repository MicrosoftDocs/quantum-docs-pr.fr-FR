---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ade0640b07f633982e98d5d02239fa205909bcce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196240"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Retourne un tableau de rotations à qubit unique le long d’un axe donné, paramétrable par des paramètres de modèle distincts.

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrée

### <a name="idxsqubits--int"></a>idxsQubits : [int](xref:microsoft.quantum.lang-ref.int)[]

Index pour le qubits à utiliser comme cibles pour chaque rotation.


### <a name="axis--pauli"></a>axe : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Axe de rotation pour chaque rotation dans la couche donnée.



## <a name="output--controlledrotation"></a>Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Tableau de rotations contrôlées sur l’axe donné, une sur chaque `nQubits` qubits.