---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 8b3d4cceb69619ed32977337fc0fe7401db38cbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211047"
---
# <a name="bitsizel-function"></a>BitSizeL fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pour un entier non négatif `a` , retourne le nombre de bits requis pour représenter `a` .

Autrement dit, retourne le plus petit $n $, ce qui $a < 2 ^ n $.

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a>Entrée

### <a name="a--bigint"></a>r : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Entier dont la taille de bits doit être calculée.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Taille de bit de `a` .