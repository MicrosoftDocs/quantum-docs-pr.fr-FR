---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Opération ApplyOpRepeatedlyOverC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 08c3af3a4877481833973061aa4d54c2b29304c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218255"
---
# <a name="applyoprepeatedlyoverc-operation"></a>Opération ApplyOpRepeatedlyOverC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique la même opération sur un registre qubit plusieurs fois.

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Entrée

### <a name="op--qubit--unit--is-ctl"></a>OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL

Opération à appliquer plusieurs fois sur le registre qubit


### <a name="targets--int"></a>cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []

Tableaux imbriqués décrivant les cibles du op. Chaque tableau doit contenir une liste de ints décrivant le qubits à utiliser.


### <a name="register--qubit"></a>Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit Inscrivez-vous pour être traité.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)