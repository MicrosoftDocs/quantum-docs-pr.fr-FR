---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Opération MaybeChooseElement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707865"
---
# <a name="maybechooseelement-operation"></a>Opération MaybeChooseElement

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Packages [](https://nuget.org/packages/)


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

