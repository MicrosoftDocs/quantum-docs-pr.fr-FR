---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Opération ApplyMajorityInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707595"
---
# <a name="applymajorityinplace-operation"></a>Opération ApplyMajorityInPlace

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Applique l’opération de qubit majoritaire sur place sur un registre de qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
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

