---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207460"
---
# <a name="composedoutput-function"></a>ComposedOutput fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la sortie de la composition de `inner` et `outer` pour une entrée donnée.

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Entrée

### <a name="outer--u---v"></a>externe : 'U-> 'V




### <a name="inner--t---u"></a>interne : t-> 'U




### <a name="target--t"></a>cible : 't





## <a name="output--v"></a>Sortie : 'V



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U


### <a name="v"></a>'V

