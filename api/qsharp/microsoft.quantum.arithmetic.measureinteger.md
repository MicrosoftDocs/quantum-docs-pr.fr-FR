---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Opération MeasureInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843121"
---
# <a name="measureinteger-operation"></a>Opération MeasureInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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