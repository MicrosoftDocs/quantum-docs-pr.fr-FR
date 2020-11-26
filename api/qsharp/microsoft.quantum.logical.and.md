---
uid: Microsoft.Quantum.Logical.And
title: Fonction and
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198569"
---
# <a name="and-function"></a>Fonction and

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la combinaison booléenne de deux valeurs.

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--bool"></a>r : [bool](xref:microsoft.quantum.lang-ref.bool)

Première valeur à prendre en compte.


### <a name="b--bool"></a>b : [bool](xref:microsoft.quantum.lang-ref.bool)

Deuxième valeur à prendre en compte.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `a` et `b` sont tous les deux `true` .

## <a name="remarks"></a>Notes

Contrairement `and` à l’opérateur, cette fonction n’a pas de court-circuit, de sorte que les deux entrées sont entièrement évaluées.

Jusqu’au comportement de court-circuit, les éléments suivants sont équivalents :

```Q#
let x = a and b;
let x = And(a, b);
```