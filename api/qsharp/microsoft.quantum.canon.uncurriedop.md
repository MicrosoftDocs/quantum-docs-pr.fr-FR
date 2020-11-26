---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204638"
---
# <a name="uncurriedop-function"></a>UncurriedOp fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>Entrée

### <a name="curriedop--t---u--unit"></a>curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit) 

Fonction qui retourne des opérations.



## <a name="output--tu--unit"></a>Sortie : ('t, 'U) => [unité](xref:microsoft.quantum.lang-ref.unit) 

Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de la première entrée d’une opération curryfiée.
### <a name="u"></a>'U

Type de la deuxième entrée d’une opération curryfiée.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft. Quantum. Canon. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft. Quantum. Canon. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)