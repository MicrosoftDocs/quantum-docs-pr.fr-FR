---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: Opération CompareGTI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: e9c245fb7c0cf3a6b1b98eb01cd582c325917602
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843299"
---
# <a name="comparegti-operation"></a>Opération CompareGTI

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Wrapper pour une comparaison d’entiers : `result = x > y` .

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Premier $n nombre de bits


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Deuxième $n nombre de $ bits


### <a name="result--qubit"></a>résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Est retourné si $x > y



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

