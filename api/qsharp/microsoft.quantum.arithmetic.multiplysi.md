---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Opération MultiplySI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706363"
---
# <a name="multiplysi-operation"></a>Opération MultiplySI

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Multiplie un entier signé `xs` par `ys` un entier signé et stocke le résultat dans `result` , qui doit être initialement de zéro.

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a>Entrée

### <a name="xs--signedlittleendian"></a>XS : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

multiplicande n bits (SignedLittleEndian)


### <a name="ys--signedlittleendian"></a>distinctes : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

multiplicateur n-bit (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>résultat : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

résultat de 2n bits (SignedLittleEndian), doit être initialement à l’État $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

