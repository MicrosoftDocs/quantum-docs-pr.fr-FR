---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: e8ce73a43940ab0ed66338f962cc6f76fc2b694b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842753"
---
# <a name="argcomplex-function"></a>ArgComplex fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la phase d’un nombre complexe de type `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Entrée

### <a name="input--complex"></a>entrée : [complexe](xref:Microsoft.Quantum.Math.Complex)

Nombre complexe $c = x + i y $.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

Phase $ \text{Arg} [c] = \text{ArcTan} (y, x) \Dans (-\pi, \pi] $.