---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: RestrictedToSubregisterA fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 28128641a95c6948b5fa5730bf3bd90aa6bb1ef5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205284"
---
# <a name="restrictedtosubregistera-function"></a>RestrictedToSubregisterA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restreint une opération à un tableau d’index d’un registre, c’est-à-dire un sous-registre.
Le modificateur `A` indique que l’opération est adjointable.

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a>Entrée

### <a name="op--qubit--unit--is-adj"></a>OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération à limiter à un sous-registre.


### <a name="idxs--int"></a>idxs : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau d’index, indiquant à quel qubits l’opération sera restreinte.



## <a name="output--qubit--unit--is-adj"></a>Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)