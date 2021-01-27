---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 2a15a749f52fe814db4fa57118f69c80fa22158a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817252"
---
# <a name="equalb-function"></a>EqualB fonction)

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur true si et seulement si deux entrées sont égales.

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--bool"></a>r : [bool](xref:microsoft.quantum.lang-ref.bool)

Première valeur à comparer.


### <a name="b--bool"></a>b : [bool](xref:microsoft.quantum.lang-ref.bool)

Deuxième valeur à comparer.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si et uniquement si `a` est égal à `b` .

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```qsharp
let cond = a == b;
let cond = EqualB(a, b);
```