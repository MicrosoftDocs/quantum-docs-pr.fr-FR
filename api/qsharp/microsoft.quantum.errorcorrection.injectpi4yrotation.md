---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Opération InjectPi4YRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702475"
---
# <a name="injectpi4yrotation-operation"></a>Opération InjectPi4YRotation

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


Fait pivoter un qubit unique par π/4 autour de l’axe Y.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
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

et

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Cette opération prend en charge `Adjoint` functor, auquel cas le même État magique est consommé, mais l’effet sur le qubit de données est un $-\ pi/4 $ $Y $-rotation.