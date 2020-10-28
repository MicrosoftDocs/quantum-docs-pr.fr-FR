---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703714"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.
Le modificateur `C` indique que les opérations sont contrôlable.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Entrée

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp : > 'U => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)

Fonction qui retourne des opérations.



## <a name="output--tu--unit-ctl"></a>Sortie : ('t, 'U) => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)

Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type du premier argument d’une fonction curryfiée.
### <a name="u"></a>'U

Type du deuxième argument d’une fonction curryfiée.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)