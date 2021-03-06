---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan, opération
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 553efb0fc83f24235cb4a77933bd1d547bbd1fed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846628"
---
# <a name="greaterthan-operation"></a>GreaterThan, opération

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une comparaison « supérieur à » entre deux entiers encodés dans des registres qubit, en retournant un qubit cible en fonction du résultat de la comparaison.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Effectue une comparaison strictement supérieure à deux entiers $x $ et $y $, encodés dans qubit inscrit XS et distinctes. Si $x > y $, le résultat qubit sera retourné, sinon le qubit de résultat conservera son état.

## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register Encoding le premier entier $x $.


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register Encoding le deuxième entier $y $.


### <a name="result--qubit"></a>résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit unique qui sera retournée si $x > y.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Utilise l’astuce qui $x-y = (x' + y) ' $, où’désigne le complément à 1.

## <a name="references"></a>Références

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton : « A New Quantum ondulation-Carry apporting circuit », 2004.
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas Haener, Martin Roetteler, Krysta M. Svore : « factorisation à l’aide de 2n + 2 qubits avec multiplication modulaire basée sur Toffoli », 2016 https://arxiv.org/abs/1611.07995