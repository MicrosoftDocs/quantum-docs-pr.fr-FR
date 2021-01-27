---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843919"
---
# <a name="standardreflectionphases-function"></a>StandardReflectionPhases fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcule les phases de réflexion partielle pour l’amplification de l’amplitude standard.

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Entrée

### <a name="niterations--int"></a>nIterations : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’itérations d’amplification d’amplitude pour générer des phases de réflexion partielles pour.



## <a name="output--reflectionphases"></a>Sortie : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Opération qui implémente des phases spécifiées en tant que réflexions partielles

## <a name="remarks"></a>Notes

Toutes les phases sont de $ \pi $, à l’exception de la première réflexion à propos de l’état de démarrage et de la dernière réflexion sur l’État cible, qui sont $0 $.