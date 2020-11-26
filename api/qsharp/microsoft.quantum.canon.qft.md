---
uid: Microsoft.Quantum.Canon.QFT
title: Opération QFT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 8f1aa8c3680a068e500503ca25afa9a49e4ef5bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205527"
---
# <a name="qft-operation"></a>Opération QFT

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Big-endian.

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="qs--bigendian"></a>QS : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registre quantique auquel la transformation de Fourier quantique est appliquée



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’entrée et la sortie sont supposées être en codage Big endian.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)