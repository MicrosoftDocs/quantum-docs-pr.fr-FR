---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Type défini par l’utilisateur RotationPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843967"
---
# <a name="rotationphases-user-defined-type"></a>Type défini par l’utilisateur RotationPhases

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Phases pour une séquence de rotations à qubit unique dans l’amplification d’amplitude.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Notes

Le premier paramètre est un tableau de phases pour les réflexions, exprimé sous la forme d’un produit de rotations à qubit unique.
[ G.H. Low, I. L. Chuang, https://arxiv.org/abs/1707.05391 ].