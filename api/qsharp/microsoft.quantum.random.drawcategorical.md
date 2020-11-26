---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Opération DrawCategorical
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192993"
---
# <a name="drawcategorical-operation"></a>Opération DrawCategorical

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dessine un échantillon aléatoire à partir d’une distribution catégorique spécifiée par une liste d’probablities.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Description

La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index.
Les éléments de tableau qui sont égaux à zéro sont ignorés et leurs index ne sont jamais retournés. Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.

## <a name="input"></a>Entrée

### <a name="probs--double"></a>sondes : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau de nombres à virgule flottante proportionnel à la probabilité de sélectionner chaque index.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Entier $i $ avec la probabilité $ \Pr (i) = p_i/\ sum_i p_i $, où $p _i $ est le $i élément $ Th de `probs` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Random. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)