---
uid: Microsoft.Quantum.Canon.Fst
title: FST, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206933"
---
# <a name="fst-function"></a>FST, fonction

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’une paire, retourne son premier élément.

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a>Entrée

### <a name="pair--tu"></a>paire : ('t, 'U)

Tuple avec deux éléments.



## <a name="output--t"></a>Sortie : 't

Premier élément de `pair`.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type du premier membre de la paire.
### <a name="u"></a>'U

Type du deuxième membre de la paire.