---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d4245437f2b71abb8bf1bbe4db43ae7d2ee23799
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845750"
---
# <a name="reversedopleca-function"></a>ReversedOpLECA fonction)

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’une opération qui prend une entrée de primauté des octets de poids faible, retourne une nouvelle opération qui prend une entrée de poids fort (Big-endian).

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="op--littleendian--unit--is-adj--ctl"></a>OP : [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian est Adj + CTL

Opération dont l’entrée doit être inversée.



## <a name="output--bigendian--unit--is-adj--ctl"></a>Sortie : [](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian est Adj + CTL

Nouvelle opération qui accepte son entrée sous la forme d’un registre Big-endian.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. ApplyReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [Microsoft. Quantum. Arithmetic. ReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [Microsoft. Quantum. Arithmetic. ReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [Microsoft. Quantum. Arithmetic. ReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)