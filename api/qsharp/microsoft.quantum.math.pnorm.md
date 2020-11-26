---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194727"
---
# <a name="pnorm-function"></a>PNorm fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la `L(p)` norme d’un vecteur de `Double` s.

Autrement dit, étant donné un tableau $x $ de type `Double[]` , le $p $-normal $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $ est retourné.

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>Entrée

### <a name="p--double"></a>p : [double](xref:microsoft.quantum.lang-ref.double)

L’exposant $p $ dans le $p $-normal.


### <a name="array--double"></a>Tableau : [double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

$P $-normal $ \| x \| _p $.