---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203227"
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

