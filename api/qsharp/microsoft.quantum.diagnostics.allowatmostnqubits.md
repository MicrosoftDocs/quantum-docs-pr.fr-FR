---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Opération AllowAtMostNQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702790"
---
# <a name="allowatmostnqubits-operation"></a>Opération AllowAtMostNQubits

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Entre un appel à cette opération et son voisin, déclare qu’au plus un nombre donné de qubits supplémentaires sont alloués avec des instructions using.

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre maximal de qubits qui peuvent être alloués.


### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)

Message à afficher en cas d’échec.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cette opération peut être remplacée par une absence d’opération sur les cibles qui ne la prennent pas en charge.