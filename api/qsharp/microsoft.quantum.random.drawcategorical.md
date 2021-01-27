---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Opération DrawCategorical
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a9fe1b08e80abc65a5c4b803f0cb8a5e7a62759c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851148"
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