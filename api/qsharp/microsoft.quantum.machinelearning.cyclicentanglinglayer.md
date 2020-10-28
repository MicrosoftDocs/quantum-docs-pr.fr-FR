---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706870"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


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