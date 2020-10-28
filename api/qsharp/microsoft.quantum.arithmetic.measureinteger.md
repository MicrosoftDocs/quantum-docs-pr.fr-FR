---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Opération MeasureInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707174"
---
# <a name="measureinteger-operation"></a>Opération MeasureInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Mesure le contenu d’un registre quantique et le convertit en entier. La mesure est effectuée par rapport à la base de calcul standard, c’est-à-dire le eigenbasis de `PauliZ` .

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>Entrée

### <a name="target--littleendian"></a>cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre quantique dans l’encodage Little-endian.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Entier non signé qui contient la valeur mesurée de `target` .

## <a name="remarks"></a>Notes

Cette opération réinitialise son registre d’entrée à l’État $ \ket{00\cdots 0} $, pouvant être republiée sur un ordinateur cible.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)