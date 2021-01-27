---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Opération ComputeReciprocalFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843259"
---
# <a name="computereciprocalfxp-operation"></a>Opération ComputeReciprocalFxP

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Calcule $1/x $ pour un nombre à virgule fixe $x $.

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="x--fixedpoint"></a>x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Nombre à virgule fixe à inverser.


### <a name="result--fixedpoint"></a>résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Nombre à virgule fixe qui contiendra le résultat. Doit être initialisé à $ \ket{0.0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

