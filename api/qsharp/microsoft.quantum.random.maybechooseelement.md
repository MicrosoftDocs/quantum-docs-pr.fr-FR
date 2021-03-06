---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Opération MaybeChooseElement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856113"
---
# <a name="maybechooseelement-operation"></a>Opération MaybeChooseElement

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


À partir d’un tableau de données et d’une distribution sur ses index, tente de choisir un élément au hasard.

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>Entrée

### <a name="data--t"></a>données : 't []

Tableau à partir duquel un élément doit être choisi.


### <a name="indexdistribution--discretedistribution"></a>indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Distribution sur les index de `data` .



## <a name="output--boolt"></a>Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="example"></a>Exemple

L’extrait de code Q # suivant choisit un élément aléatoire dans un tableau :

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```