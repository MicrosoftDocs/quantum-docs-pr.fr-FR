---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707733"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Packages [](https://nuget.org/packages/)


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