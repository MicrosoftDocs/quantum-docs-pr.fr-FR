---
uid: Microsoft.Quantum.Logical.Not
title: Not, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197447"
---
# <a name="not-function"></a>Not, fonction

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la négation booléenne d’une valeur.

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>Entrée

### <a name="value--bool"></a>valeur : [bool](xref:microsoft.quantum.lang-ref.bool)

Valeur à rendre négative.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `value` est `false` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```Q#
let x = not value;
let x = Not(value);
```