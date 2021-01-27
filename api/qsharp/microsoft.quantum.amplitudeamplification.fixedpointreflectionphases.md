---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845859"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcule les phases de réflexion partielle pour l’amplification de l’amplitude à virgule fixe.

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Entrée

### <a name="nqueries--int"></a>nQueries : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de requêtes à la préparation de l’État Oracle. Doit être un entier impair.


### <a name="successmin--double"></a>successMin : [double](xref:microsoft.quantum.lang-ref.double)

Probabilité de réussite minimale cible.



## <a name="output--reflectionphases"></a>Sortie : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Tableau de phases qui peut être utilisé dans l’implémentation de l’algorithme Quantum d’amplification à virgule fixe.

## <a name="references"></a>Références

Nous utilisons les phases de « amplification de l’amplitude à virgule fixe avec un nombre optimal de requêtes »

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Voir aussi « méthodologie des portes Quantum composites »
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) pour les phases au `RotationPhases` format.