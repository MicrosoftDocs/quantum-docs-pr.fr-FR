---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847380"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Retourne un tableau de rotations contrôlées de façon unique le long d’un axe donné, organisées de façon cyclique sur un registre de qubits et paramétrables par des paramètres de modèle distincts.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits traités par la couche donnée.


### <a name="axis--pauli"></a>axe : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Axe de rotation pour chaque rotation dans la couche donnée.


### <a name="stride--int"></a>STRIDE : [int](xref:microsoft.quantum.lang-ref.int)

Séparation entre les index cible et de contrôle pour chaque rotation.



## <a name="output--controlledrotation"></a>Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Tableau de rotations contrôlées par deux qubit disposées de façon cyclique sur un registre de `nQubits` qubits.

## <a name="example"></a>Exemple

Les éléments suivants sont équivalents :

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```