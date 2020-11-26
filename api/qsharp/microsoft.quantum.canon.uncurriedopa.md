---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204621"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.
Le modificateur `A` indique que les opérations sont adjointable.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Entrée

### <a name="curriedop--t---u--unit--is-adj"></a>curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Fonction qui retourne des opérations.



## <a name="output--tu--unit--is-adj"></a>Sortie : ('t, 'U) => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type du premier argument d’une fonction curryfiée.
### <a name="u"></a>'U

Type du deuxième argument d’une fonction curryfiée.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)