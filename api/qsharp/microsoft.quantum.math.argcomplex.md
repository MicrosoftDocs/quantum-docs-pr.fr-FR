---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708336"
---
# <a name="argcomplex-function"></a>ArgComplex fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


Retourne la phase d’un nombre complexe de type `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Entrée

### <a name="input--complex"></a>entrée : [complexe](xref:Microsoft.Quantum.Math.Complex)

Nombre complexe $c = x + i y $.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

Phase $ \text{Arg} [c] = \text{ArcTan} (y, x) \Dans (-\pi, \pi] $.