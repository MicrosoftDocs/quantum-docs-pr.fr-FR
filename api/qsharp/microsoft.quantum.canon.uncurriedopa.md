---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703717"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.
Le modificateur `A` indique que les opérations sont adjointable.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Entrée

### <a name="curriedop--t---u--unit-adj"></a>curriedOp : > 'U => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Fonction qui retourne des opérations.



## <a name="output--tu--unit-adj"></a>Sortie : ('t, 'U) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type du premier argument d’une fonction curryfiée.
### <a name="u"></a>'U

Type du deuxième argument d’une fonction curryfiée.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)