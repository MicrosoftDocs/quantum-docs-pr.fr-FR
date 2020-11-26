---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: Opération ApplyReversedOpBECA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 5c761fb8e1042a25cd2e88f1b33e597c7d9287f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202717"
---
# <a name="applyreversedopbeca-operation"></a>Opération ApplyReversedOpBECA

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération qui prend une entrée de poids fort (Big-endian) à un registre qui encode un entier non signé utilisant le format Little endian.

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="op--bigendian--unit--is-adj--ctl"></a>OP : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian est Adj + CTL

Opération qui agit sur un registre Big endian.


### <a name="register--littleendian"></a>inscription : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre Little endian à transformer.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. ApplyReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [Microsoft. Quantum. Arithmetic. ApplyReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [Microsoft. Quantum. Arithmetic. ApplyReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)