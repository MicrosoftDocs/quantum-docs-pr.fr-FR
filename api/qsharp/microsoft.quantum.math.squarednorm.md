---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848214"
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