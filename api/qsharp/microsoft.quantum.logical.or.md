---
uid: Microsoft.Quantum.Logical.Or
title: Fonction or
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197124"
---
# <a name="or-function"></a>Fonction or

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la disjonction booléenne de deux valeurs.

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--bool"></a>r : [bool](xref:microsoft.quantum.lang-ref.bool)

Première valeur à prendre en compte.


### <a name="b--bool"></a>b : [bool](xref:microsoft.quantum.lang-ref.bool)

Deuxième valeur à prendre en compte.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et uniquement si `a` ou ont la valeur `b` `true` .

## <a name="remarks"></a>Notes

Contrairement `or` à l’opérateur, cette fonction n’a pas de court-circuit, de sorte que les deux entrées sont entièrement évaluées.

Jusqu’au comportement de court-circuit, les éléments suivants sont équivalents :

```Q#
let x = a or b;
let x = Or(a, b);
```