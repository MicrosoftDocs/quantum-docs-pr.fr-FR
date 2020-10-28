---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Type défini par l’utilisateur RotationPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707694"
---
# <a name="rotationphases-user-defined-type"></a>Type défini par l’utilisateur RotationPhases

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Packages [](https://nuget.org/packages/)


Phases pour une séquence de rotations à qubit unique dans l’amplification d’amplitude.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Notes

Le premier paramètre est un tableau de phases pour les réflexions, exprimé sous la forme d’un produit de rotations à qubit unique.
[ G.H. Low, I. L. Chuang, https://arxiv.org/abs/1707.05391 ].