---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 3a4872be6b81498c26ab9a14134940c5ef8628b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706286"
---
# <a name="reversedoplec-function"></a>ReversedOpLEC fonction)

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


À partir d’une opération qui prend une entrée de primauté des octets de poids faible, retourne une nouvelle opération qui prend une entrée de poids fort (Big-endian).

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a>Entrée

### <a name="op--littleendian--unit-ctl"></a>OP : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) d' => [unités](xref:microsoft.quantum.lang-ref.unit) CTL

Opération dont l’entrée doit être inversée.



## <a name="output--bigendian--unit-ctl"></a>Sortie : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => liste CTL d' [unités](xref:microsoft.quantum.lang-ref.unit) bigEndian

Nouvelle opération qui accepte son entrée sous la forme d’un registre Big-endian.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. ApplyReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [Microsoft. Quantum. Arithmetic. ReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [Microsoft. Quantum. Arithmetic. ReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [Microsoft. Quantum. Arithmetic. ReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)