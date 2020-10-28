---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 21c9cdfc3b5b266cb3b93e52ee2fa4c655caf795
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703759"
---
# <a name="transformedoperationca-function"></a>TransformedOperationCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


À partir d’une fonction et d’une opération, retourne une nouvelle opération dont l’entrée est transformée par la fonction donnée.

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="fn--u---t"></a>FN : 'U-> '

Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.


### <a name="op--t--unit-adj--ctl"></a>OP : t [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL

Opération à transformer.



## <a name="output--u--unit-adj--ctl"></a>Sortie : 'U => ajustable d' [unité](xref:microsoft.quantum.lang-ref.unit) + CTL

Une nouvelle opération tbat appelle `fn` avec son entrée, puis passe la sortie obtenue à `op` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. Quantum. Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. composed](xref:Microsoft.Quantum.Canon.Composed)