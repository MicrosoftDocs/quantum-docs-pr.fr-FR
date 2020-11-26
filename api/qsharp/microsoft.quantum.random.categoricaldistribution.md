---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210248"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution fonction)

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Retourne une distribution catégorique discrète, dans laquelle la probabilité pour chaque liste finie de résultats donnés est explicitement spécifiée.

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Entrée

### <a name="probs--double"></a>sondes : [double](xref:microsoft.quantum.lang-ref.double)[]

Probabilités pour chaque résultat de la distribution catégorique.
Ces probabilités ne peuvent pas être normalisées, mais elles doivent toutes être non négatives.



## <a name="output--discretedistribution"></a>Sortie : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Index `i` avec la probabilité `probs[i] / sum` , où `sum` est la somme de `probs` donnée par `Fold(PlusD, 0.0, probs)` .