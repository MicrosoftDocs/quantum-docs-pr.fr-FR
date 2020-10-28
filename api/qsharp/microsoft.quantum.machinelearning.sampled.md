---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Fonction échantillonnée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707976"
---
# <a name="sampled-function"></a>Fonction échantillonnée

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Échantillonne un tableau donné, à l’aide de la planification donnée.

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="schedule--samplingschedule"></a>planification : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Planification à utiliser dans les valeurs d’échantillonnage.


### <a name="values--t"></a>valeurs : 't []

Tableau de valeurs à échantillonner.



## <a name="output--t"></a>Sortie : 't []

Tableau d’éléments à partir de valeurs, suivant la planification donnée.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

