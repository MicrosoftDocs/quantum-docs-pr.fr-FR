---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Type défini par l’utilisateur ControlledRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702064"
---
# <a name="controlledrotation-user-defined-type"></a>Type défini par l’utilisateur ControlledRotation

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Décrit une rotation contrôlée en termes de l’index de la cible et du contrôle, de l’axe de rotation et de l’index dans un vecteur de paramètre de modèle.

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>Éléments nommés

### <a name="targetindex--int"></a>TargetIndex : [entier](xref:microsoft.quantum.lang-ref.int)

Index du qubit cible pour cette rotation contrôlée.
### <a name="controlindices--int"></a>ControlIndices : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau des index de qubit de contrôle pour cette rotation.
### <a name="axis--pauli"></a>Axe : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Axe pour cette rotation.
### <a name="parameterindex--int"></a>ParameterIndex : [entier](xref:microsoft.quantum.lang-ref.int)

Index dans un vecteur de paramètre de modèle décrivant l’angle de cette rotation.

## <a name="remarks"></a>Notes

Une rotation non contrôlée peut être représentée en affectant `ControlIndices` à un tableau vide d’index, `new Int[0]` .