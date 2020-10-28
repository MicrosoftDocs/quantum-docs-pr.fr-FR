---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707916"
---
# <a name="pnormalized-function"></a>PNormalized fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


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