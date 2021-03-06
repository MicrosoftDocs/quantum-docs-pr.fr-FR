---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Opération InjectPi4YRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825942"
---
# <a name="injectpi4yrotation-operation"></a>Opération InjectPi4YRotation

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fait pivoter un qubit unique par π/4 autour de l’axe Y.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a>Description

Effectue une rotation π/4 autour de `Y` .

La rotation est effectuée en consommant un État magique ; autrement dit, une copie de l’État $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .
\end{align} $ $

## <a name="input"></a>Entrée

### <a name="data--qubit"></a>données : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit à faire pivoter sur $Y $ par $ \pi/$4.


### <a name="magic--qubit"></a>magie : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Un qubit initialement dans l’État magique. L’application suivante de cette opération, `magic` est retournée à l' {0} État $ \ket $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```qsharp
Ry(PI() / 4.0, data);
```

and

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Cette opération prend en charge `Adjoint` functor, auquel cas le même État magique est consommé, mais l’effet sur le qubit de données est un $-\ pi/4 $ $Y $-rotation.