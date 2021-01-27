---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: Opération ApplyToEachA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844614"
---
# <a name="applytoeacha-operation"></a>Opération ApplyToEachA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération à qubit unique à chaque élément d’un registre.
Le modificateur `A` indique que l’opération à qubit unique est adjointable.

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="singleelementoperation--t--unit--is-adj"></a>singleElementOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération à appliquer à chaque qubit.


### <a name="register--t"></a>inscrire : 't []

Tableau de qubits sur lequel appliquer l’opération donnée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle l’opération agit.

## <a name="example"></a>Exemple

Préparez un état de trois-qubit $ \ket{+} $ :

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)