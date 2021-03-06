---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Type défini par l’utilisateur ControlledRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847394"
---
# <a name="controlledrotation-user-defined-type"></a>Type défini par l’utilisateur ControlledRotation

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

## <a name="example"></a>Exemple

L’exemple suivant représente une rotation à propos du $X $-AXIS du premier qubit dans un registre, contrôlé sur le deuxième qubit, et avec un angle donné par le quatrième paramètre dans un modèle séquentiel :

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>Notes

Une rotation non contrôlée peut être représentée en affectant `ControlIndices` à un tableau vide d’index, `new Int[0]` .