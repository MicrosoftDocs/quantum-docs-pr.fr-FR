---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814421"
---
# <a name="notequalb-function"></a>NotEqualB fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur true si et seulement si deux entrées ne sont pas égales.

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--bool"></a>r : [bool](xref:microsoft.quantum.lang-ref.bool)

Première valeur à comparer.


### <a name="b--bool"></a>b : [bool](xref:microsoft.quantum.lang-ref.bool)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et seulement si `a` n’est pas égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```