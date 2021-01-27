---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Opération ApplyMajorityInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843724"
---
# <a name="applymajorityinplace-operation"></a>Opération ApplyMajorityInPlace

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique l’opération de qubit majoritaire sur place sur un registre de qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Cette opération calcule la fonction majoritaire sur place sur 3 qubits.

Si vous désignez la sortie qubit comme $z $ et l’entrée qubits $x $ et $y $, l’opération effectue la transformation suivante : $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Entrée

### <a name="output--qubit"></a>sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Premier qubit d’entrée. Notez que la sortie est calculée sur place et stockée dans ce qubit.


### <a name="input--qubit"></a>entrée : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Deuxième et troisième qubits d’entrée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

