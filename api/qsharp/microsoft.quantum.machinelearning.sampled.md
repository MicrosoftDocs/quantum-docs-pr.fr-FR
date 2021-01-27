---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Fonction échantillonnée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854945"
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

