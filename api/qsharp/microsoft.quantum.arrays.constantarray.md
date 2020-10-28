---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706139"
---
# <a name="constantarray-function"></a>ConstantArray fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


Crée un tableau de longueur donnée avec tous les éléments égaux à la valeur donnée.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="length--int"></a>Longueur : [int](xref:microsoft.quantum.lang-ref.int)

Longueur du nouveau tableau.


### <a name="value--t"></a>valeur : 't

Valeur de chaque élément du nouveau tableau.



## <a name="output--t"></a>Sortie : 't []

Nouveau tableau de longueur `length` , de telle sorte que chaque élément est `value` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

