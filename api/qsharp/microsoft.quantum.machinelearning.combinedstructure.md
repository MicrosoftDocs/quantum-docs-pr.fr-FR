---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706875"
---
# <a name="combinedstructure-function"></a>CombinedStructure fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


À partir d’une ou plusieurs couches de rotations contrôlées, retourne une couche unique avec un index de paramètre de modèle décalé de telle sorte que des couches distinctes sont paramétrables par des paramètres de modèle distincts.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrée

### <a name="layers--controlledrotation"></a>couches : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

Couches à combiner.



## <a name="output--controlledrotation"></a>Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Couche unique de rotations contrôlées, représentant la concaténation de toutes les autres couches.