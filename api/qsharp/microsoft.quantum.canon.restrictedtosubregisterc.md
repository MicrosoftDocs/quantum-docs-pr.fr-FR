---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2ca32cf8c85f33f498a30f71833b3dd69db6da6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703843"
---
# <a name="restrictedtosubregisterc-function"></a>RestrictedToSubregisterC fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Restreint une opération à un tableau d’index d’un registre, c’est-à-dire un sous-registre.
Le modificateur `C` indique que l’opération est contrôlable.

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a>Entrée

### <a name="op--qubit--unit-ctl"></a>OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération à limiter à un sous-registre.


### <a name="idxs--int"></a>idxs : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau d’index, indiquant à quel qubits l’opération sera restreinte.



## <a name="output--qubit--unit-ctl"></a>Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)