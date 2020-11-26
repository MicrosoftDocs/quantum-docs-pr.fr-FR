---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227299"
---
# <a name="squarednorm-function"></a>SquaredNorm fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne le carré 2-norme d’un vecteur.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Description

Retourne le carré 2-norme d’un vecteur ; autrement dit, étant donné une entrée $ \vec{x} $, retourne $ \ sum_i x_i ^ 2 $.

## <a name="input"></a>Entrée

### <a name="array--double"></a>Tableau : [double](xref:microsoft.quantum.lang-ref.double)[]

Vecteur dont la norme quadratique 2 doit être retournée.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

La norme quadratique 2 de `array` .