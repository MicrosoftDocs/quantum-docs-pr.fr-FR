---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Opération MultiplySI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7c7e7dfaee9b9dc717db44956506984e60281dd2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843014"
---
# <a name="multiplysi-operation"></a>Opération MultiplySI

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Multiplie un entier signé `xs` par `ys` un entier signé et stocke le résultat dans `result` , qui doit être initialement de zéro.

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="xs--signedlittleendian"></a>XS : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

multiplicande n bits (SignedLittleEndian)


### <a name="ys--signedlittleendian"></a>distinctes : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

multiplicateur n-bit (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>résultat : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

résultat de 2n bits (SignedLittleEndian), doit être initialement à l’État $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

