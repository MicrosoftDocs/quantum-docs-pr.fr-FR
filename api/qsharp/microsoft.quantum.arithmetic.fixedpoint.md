---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Type défini par l’utilisateur FixedPoint
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843200"
---
# <a name="fixedpoint-user-defined-type"></a>Type défini par l’utilisateur FixedPoint

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Représente un registre de qubits codant un nombre à virgule fixe. Se compose d’un entier qui est égal au nombre de qubits à gauche du point binaire, c’est-à-dire qubits de poids supérieur ou égal à 1, et d’un registre quantique.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

