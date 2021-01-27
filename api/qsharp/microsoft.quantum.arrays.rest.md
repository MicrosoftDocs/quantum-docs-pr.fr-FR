---
uid: Microsoft.Quantum.Arrays.Rest
title: Fonction Rest
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845473"
---
# <a name="rest-function"></a>Fonction Rest

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crée un tableau qui est égal à un tableau d’entrée, sauf que le premier élément de tableau est supprimé.

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="array--t"></a>Tableau : 't []

Tableau dont l’avant-dernier élément doit former le tableau de sortie.



## <a name="output--t"></a>Sortie : 't []

Tableau contenant les éléments `array[1..Length(array) - 1]` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des éléments du tableau.