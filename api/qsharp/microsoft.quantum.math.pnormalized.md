---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854852"
---
# <a name="pnormalized-function"></a>PNormalized fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Normalise un vecteur de `Double` s dans la `L(p)` norme.

Autrement dit, étant donné un tableau $x $ de type `Double[]` , retourne un tableau où tous les éléments sont divisés par le $p $-normal $ \| x \| _p $.

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>Entrée

### <a name="p--double"></a>p : [double](xref:microsoft.quantum.lang-ref.double)

L’exposant $p $ dans le $p $-normal.


### <a name="array--double"></a>Tableau : [double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]

Le tableau $x $ normalized par la $p $-Normalize $ \| x \| _p $.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Math. PNorm](xref:Microsoft.Quantum.Math.PNorm)