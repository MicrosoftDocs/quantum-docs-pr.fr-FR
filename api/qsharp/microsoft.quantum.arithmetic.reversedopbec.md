---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5e9aa6e6dfef74bca004170cf2b1cd91aa13f0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706315"
---
# <a name="reversedopbec-function"></a>ReversedOpBEC fonction)

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


À partir d’une opération qui prend une entrée de poids fort, retourne une nouvelle opération qui prend une entrée de primauté des octets de poids faible.

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a>Entrée

### <a name="op--bigendian--unit-ctl"></a>OP : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) d' => [unités](xref:microsoft.quantum.lang-ref.unit) CTL

Opération dont l’entrée doit être inversée.



## <a name="output--littleendian--unit-ctl"></a>Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => liste CTL d' [unités](xref:microsoft.quantum.lang-ref.unit) LittleEndian

Nouvelle opération qui accepte son entrée comme Registre Little endian.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. ApplyReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [Microsoft. Quantum. Arithmetic. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. Quantum. Arithmetic. ReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [Microsoft. Quantum. Arithmetic. ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)