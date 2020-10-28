---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706326"
---
# <a name="reversedopbea-function"></a>ReversedOpBEA fonction)

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


À partir d’une opération qui prend une entrée de poids fort, retourne une nouvelle opération qui prend une entrée de primauté des octets de poids faible.

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a>Entrée

### <a name="op--bigendian--unit-adj"></a>opération : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian

Opération dont l’entrée doit être inversée.



## <a name="output--littleendian--unit-adj"></a>Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian

Nouvelle opération qui accepte son entrée comme Registre Little endian.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. ApplyReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [Microsoft. Quantum. Arithmetic. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. Quantum. Arithmetic. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [Microsoft. Quantum. Arithmetic. ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)