---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211098"
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