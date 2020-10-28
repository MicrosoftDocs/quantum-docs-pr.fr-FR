---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: Opération ComputeReciprocalI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707347"
---
# <a name="computereciprocali-operation"></a>Opération ComputeReciprocalI

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Calcule la valeur réciproque 1/x pour un entier non signé x à l’aide de la Division d’entiers. Le résultat, interprété comme un entier, sera `floor(2^(2*n-1) / x)` .

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

entier non signé n bits


### <a name="result--littleendian"></a>résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

la sortie 2n bits doit se trouver au début de $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Pour l’entrée x = 0, la sortie sera tous les éléments.