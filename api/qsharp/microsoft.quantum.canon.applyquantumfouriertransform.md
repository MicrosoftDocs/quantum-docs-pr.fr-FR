---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Opération ApplyQuantumFourierTransform
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 6d3ad9ca2e0d10c264f8020e1f34687f6cbc9f94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218187"
---
# <a name="applyquantumfouriertransform-operation"></a>Opération ApplyQuantumFourierTransform

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Little endian.

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="qs--littleendian"></a>QS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre quantique auquel la transformation de Fourier quantique est appliquée



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’entrée et la sortie sont supposées être dans un encodage Little endian.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)