---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Opération CompareGTSI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707382"
---
# <a name="comparegtsi-operation"></a>Opération CompareGTSI

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Wrapper pour comparaison d’entiers signés : `result = xs > ys` .

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a>Entrée

### <a name="xs--signedlittleendian"></a>XS : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Premier $n nombre de bits


### <a name="ys--signedlittleendian"></a>distinctes : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Deuxième $n nombre de $ bits


### <a name="result--qubit"></a>résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Est retourné si $xs > distinctes $



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

