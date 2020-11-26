---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: abbbd367859952180f181a245ca0754646529b18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210707"
---
# <a name="extendedgreatestcommondivisorl-function"></a>ExtendedGreatestCommonDivisorL fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcule un tuple $ (u, v) $ de sorte que $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, où $ \operatorname{GCD} $ est $a le plus grand diviseur commun de $a $ et $b $. Le GCD est toujours positif.

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>Entrée

### <a name="a--bigint"></a>r : [bigint](xref:microsoft.quantum.lang-ref.bigint)

premier nombre duquel le plus grand commun diviseur est calculé


### <a name="b--bigint"></a>b : [bigint](xref:microsoft.quantum.lang-ref.bigint)

deuxième nombre duquel le plus grand commun diviseur est calculé



## <a name="output--bigintbigint"></a>Sortie : ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))

Tuple $ (u, v) $ avec la propriété $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.

## <a name="references"></a>Références

- Cette implémentation est conforme à https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm