---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: feb5da771ee6cb6a750fa76f9ffd8f5a3e0b5734
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840051"
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