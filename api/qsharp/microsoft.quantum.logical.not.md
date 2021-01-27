---
uid: Microsoft.Quantum.Logical.Not
title: Not, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849088"
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

```qsharp
let x = not value;
let x = Not(value);
```