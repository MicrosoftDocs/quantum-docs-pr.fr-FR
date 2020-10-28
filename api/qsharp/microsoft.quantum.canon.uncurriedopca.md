---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703711"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.
Le modificateur `CA` indique que les opérations sont contrôlable et adjointable.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrée

### <a name="curriedop--t---u--unit-ctl--adj"></a>curriedOp : 't-> 'U => d' [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj

Fonction qui retourne des opérations.



## <a name="output--tu--unit-ctl--adj"></a>Sortie : ('t, 'U) => d' [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj

Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type du premier argument d’une fonction curryfiée.
### <a name="u"></a>'U

Type du deuxième argument d’une fonction curryfiée.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)