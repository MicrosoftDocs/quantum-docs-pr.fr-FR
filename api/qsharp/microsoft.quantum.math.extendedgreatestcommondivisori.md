---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195525"
---
# <a name="extendedgreatestcommondivisori-function"></a>ExtendedGreatestCommonDivisorI fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcule un tuple $ (u, v) $ de sorte que $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, où $ \operatorname{GCD} $ est $a le plus grand diviseur commun de $a $ et $b $. Le GCD est toujours positif.

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>Entrée

### <a name="a--int"></a>r : [entier](xref:microsoft.quantum.lang-ref.int)

premier nombre duquel le plus grand commun diviseur est calculé


### <a name="b--int"></a>b : [entier](xref:microsoft.quantum.lang-ref.int)

deuxième nombre duquel le plus grand commun diviseur est calculé



## <a name="output--intint"></a>Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Tuple $ (u, v) $ avec la propriété $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.

## <a name="references"></a>Références

- Cette implémentation est conforme à https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm