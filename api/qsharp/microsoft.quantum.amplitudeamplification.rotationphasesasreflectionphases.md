---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707688"
---
# <a name="rotationphasesasreflectionphases-function"></a>RotationPhasesAsReflectionPhases fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Packages [](https://nuget.org/packages/)


Convertit les phases spécifiées sous forme de rotations de qubit simple en phases spécifiées comme réflexions partielles.

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Entrée

### <a name="rotphases--rotationphases"></a>rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)

Tableau de rotations à qubit unique à convertir en réflexions partielles.



## <a name="output--reflectionphases"></a>Sortie : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Opération qui implémente des phases spécifiées en tant que réflexions partielles.

## <a name="references"></a>Références

Nous utilisons la Convention dans

- [ *G.H. Low, I. L. Chuang*](https://arxiv.org/abs/1707.05391) pour la liaison des phases de rotation simple qubit aux phases d’opérateur de réflexion.