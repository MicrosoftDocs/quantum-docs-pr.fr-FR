---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Opération ApplyIfA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 8bdca1bf286d564dfbb540bc9d63c035d2196f00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845037"
---
# <a name="applyifa-operation"></a>Opération ApplyIfA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération adjointable conditionnée sur un bit classique.

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a>Description

Pour une opération donnée `op` et une valeur de bit `bit` , s’applique `op` à `target` si `bit` est `true` . Si `false` , rien ne se passe au `target` .
Le suffixe `A` indique que l’opération à appliquer est adjointable.

## <a name="input"></a>Entrée

### <a name="op--t--unit--is-adj"></a>OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération à appliquer de manière conditionnelle.


### <a name="bit--bool"></a>bit : [bool](xref:microsoft.quantum.lang-ref.bool)

valeur booléenne qui contrôle si l’opération est appliquée ou non.


### <a name="target--t"></a>cible : 't

Entrée à laquelle l’opération est appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à appliquer de façon conditionnelle.

## <a name="example"></a>Exemple

L’exemple suivant prépare un registre de qubits dans un état de base de calcul représenté par une chaîne de bits classique donnée sous la forme d’un tableau de `Bool` valeurs :

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. Quantum. Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. Quantum. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)