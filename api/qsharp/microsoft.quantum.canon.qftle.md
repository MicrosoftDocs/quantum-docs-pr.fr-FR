---
uid: Microsoft.Quantum.Canon.QFTLE
title: Opération QFTLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703897"
---
# <a name="qftle-operation"></a>Opération QFTLE

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Little endian.

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Entrée

### <a name="qs--littleendian"></a>QS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre quantique auquel la transformation de Fourier quantique est appliquée



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’entrée et la sortie sont supposées être dans un encodage Little endian.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)