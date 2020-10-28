---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709089"
---
# <a name="squarednorm-function"></a>SquaredNorm fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


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