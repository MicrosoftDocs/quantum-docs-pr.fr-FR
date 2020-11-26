---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Fonction échantillonnée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211625"
---
# <a name="sampled-function"></a>Fonction échantillonnée

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

