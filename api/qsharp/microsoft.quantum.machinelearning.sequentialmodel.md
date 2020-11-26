---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Type défini par l’utilisateur SequentialModel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196172"
---
# <a name="sequentialmodel-user-defined-type"></a>Type défini par l’utilisateur SequentialModel

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Décrit un modèle de classifieur Quantum composé d’une séquence de rotations paramétrées et contrôlées, d’une assignation d’angles de rotation et d’un décalage entre les deux classes reconnues par le modèle.

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Éléments nommés

### <a name="structure--controlledrotation"></a>Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Séquence de rotations contrôlées utilisées pour classer les entrées.
### <a name="parameters--double"></a>Paramètres : [double](xref:microsoft.quantum.lang-ref.double)[]

Assignation d’angles de rotation à la structure de classification donnée.
### <a name="bias--double"></a>Biais : [double](xref:microsoft.quantum.lang-ref.double)

Décalage entre les deux classes reconnues par ce classifieur.

## <a name="references"></a>Références

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)