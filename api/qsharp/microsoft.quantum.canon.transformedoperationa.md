---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: eceba260e601b73bdfa2de6ea6ab146820b5c59a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204876"
---
# <a name="transformedoperationa-function"></a>TransformedOperationA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’une fonction et d’une opération, retourne une nouvelle opération dont l’entrée est transformée par la fonction donnée.

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a>Entrée

### <a name="fn--u---t"></a>FN : 'U-> '

Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.


### <a name="op--t--unit--is-adj"></a>OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération à transformer.



## <a name="output--u--unit--is-adj"></a>Sortie : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Une nouvelle opération tbat appelle `fn` avec son entrée, puis passe la sortie obtenue à `op` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. Quantum. Canon. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. composed](xref:Microsoft.Quantum.Canon.Composed)