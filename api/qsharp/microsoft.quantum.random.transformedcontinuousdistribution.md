---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701884"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution fonction)

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Packages [](https://nuget.org/packages/)


À partir d’une distribution continue, retourne une nouvelle distribution qui transforme l’original par une fonction donnée.

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Entrée

### <a name="transform--double---double"></a>transformation : [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)

Fonction qui transforme les variates de la distribution d’origine en distribution transformée.


### <a name="distribution--continuousdistribution"></a>distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Distribution d’origine à transformer.



## <a name="output--continuousdistribution"></a>Sortie : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Nouvelle distribution liée à `distribution` par la transformation donnée par `transform` .