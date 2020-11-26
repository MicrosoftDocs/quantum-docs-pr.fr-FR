---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Opération AllowAtMostNQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202547"
---
# <a name="allowatmostnqubits-operation"></a>Opération AllowAtMostNQubits

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Entre un appel à cette opération et son voisin, déclare qu’au plus un nombre donné de qubits supplémentaires sont alloués avec des instructions using.

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre maximal de qubits qui peuvent être alloués.


### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)

Message à afficher en cas d’échec.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cette opération peut être remplacée par une absence d’opération sur les cibles qui ne la prennent pas en charge.