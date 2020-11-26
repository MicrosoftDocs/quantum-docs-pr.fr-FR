---
uid: Microsoft.Quantum.Canon.QFTLE
title: Opération QFTLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 460e43bc7997e9efad06c58ad14822e28cc45cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205573"
---
# <a name="qftle-operation"></a>Opération QFTLE

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Little endian.

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="qs--littleendian"></a>QS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre quantique auquel la transformation de Fourier quantique est appliquée



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’entrée et la sortie sont supposées être dans un encodage Little endian.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)