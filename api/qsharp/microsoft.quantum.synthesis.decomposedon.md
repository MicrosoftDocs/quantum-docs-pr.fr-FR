---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855530"
---
# <a name="decomposedon-function"></a>DecomposedOn fonction)

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Décompose une permutation sur une variable

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Description

Étant donné une permutation $ \pi $ ( `perm` ) et un index $i $ ( `index` ), cette méthode retourne trois permutations $ ((\ pi_l, \ Pi_R), \pi') $, de telle sorte que les images de $ \ pi_l $ et $ \ Pi_R $ ne changent pas les bits dans leurs éléments aux index autres que $i $ et les images de $ \pi' $ ne changent pas le bit $i $ dans leurs éléments.

## <a name="input"></a>Entrée

### <a name="perm--int"></a>Perm : [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index : [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Sortie : (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])



## <a name="example"></a>Exemple

Supposons que l’entrée est Perm = [0, 2, 3, 5, 7, 1, 4, 6] et index = 0, alors cette fonction calcule trois permutations basées sur le tableau suivant, qui répertorie la permutation `perm` en notation binaire avec les éléments dans le groupe A et les images dans le groupe D.  Les colonnes répertorient les index binaires.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

Toutes les valeurs des index qui ne sont pas égales à 0 (= index) sont copiées de A à B et de D à C.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

Ensuite, la valeur 0 est placée pour le premier élément avec un index vide à la colonne 0 du bloc B, puis 1 est placé dans B où le préfixe correspond (dans le premier cas, l’autre ligne avec les index 0 0).
Ensuite, un 1 est ajouté à la même ligne dans le bloc C, puis 0 pour le préfixe correspondant dans le bloc C.  Ce processus est répété, jusqu’à ce que tous les index aient été placés dans la colonne 0 des blocs B et C.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

Nous pouvons lire trois nouvelles permutations à partir de la table :

- $ \ pi_l $ avec les éléments d’un, images en B (à gauche)
- $ \ pi_r $ avec des éléments dans D, images en C (à droite)
- $ \pi' $ avec des éléments dans B, images en C (reste)

Notez que les valeurs de bit de conception ne changent pas dans $ \ pi_l $ et $ \ pi_r $ pour les index 1 et 2, et les valeurs de bit ne changent pas pour dans $ \ pi_ ' $ pour l’index 0.  Notez également que $ \ pi_l $ et $ \ pi_r $ doivent être auto-inverses.

Les permutations dérivées et retournées sont : Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] reste = [0, 3, 2, 5, 6, 1, 4, 7]