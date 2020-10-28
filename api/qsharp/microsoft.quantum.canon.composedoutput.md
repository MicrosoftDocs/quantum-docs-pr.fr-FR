---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704350"
---
# <a name="composedoutput-function"></a>ComposedOutput fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


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

