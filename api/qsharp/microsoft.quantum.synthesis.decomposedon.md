---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709173"
---
# <a name="decomposedon-function"></a>DecomposedOn fonction)

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Packages [](https://nuget.org/packages/)


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

