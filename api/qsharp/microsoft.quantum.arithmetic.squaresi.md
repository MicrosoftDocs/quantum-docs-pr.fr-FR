---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Opération squarei
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706219"
---
# <a name="squaresi-operation"></a>Opération squarei

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Entier signé carré `xs` et stocke le résultat dans `result` , qui doit être initialement de zéro.

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a>Entrée

### <a name="xs--signedlittleendian"></a>XS : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

entier n-bit vers carré (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>résultat : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

résultat de 2n bits (SignedLittleEndian), doit être initialement à l’État $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’implémentation s’appuie sur IntegerSquare.