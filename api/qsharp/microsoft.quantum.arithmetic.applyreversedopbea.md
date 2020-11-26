---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: Opération ApplyReversedOpBEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 17d05e0914eead28ff0e04b858b003659d37ab7f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202819"
---
# <a name="applyreversedopbea-operation"></a>Opération ApplyReversedOpBEA

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération qui prend une entrée de poids fort (Big-endian) à un registre qui encode un entier non signé utilisant le format Little endian.

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="op--bigendian--unit--is-adj"></a>OP : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian est ajustée

Opération qui agit sur un registre Big endian.


### <a name="register--littleendian"></a>inscription : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre Little endian à transformer.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. ApplyReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [Microsoft. Quantum. Arithmetic. ApplyReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [Microsoft. Quantum. Arithmetic. ApplyReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)