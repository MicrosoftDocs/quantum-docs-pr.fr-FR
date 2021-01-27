---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842343"
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

## <a name="example"></a>Exemple

Le code Q # suivant affiche 0 avec une probabilité de 30% et 1 avec une probabilité de 70% :

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```