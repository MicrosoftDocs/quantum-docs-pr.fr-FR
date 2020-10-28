---
uid: Microsoft.Quantum.Arrays.Most
title: La plupart des fonctions
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705862"
---
# <a name="most-function"></a>La plupart des fonctions

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


Crée un tableau qui est égal à un tableau d’entrée, sauf que le dernier élément de tableau est supprimé.

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="array--t"></a>Tableau : 't []

Tableau dont le premier à l’avant-dernier élément doit former le tableau de sortie.



## <a name="output--t"></a>Sortie : 't []

Tableau contenant les éléments `array[0..Length(array) - 2]` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des éléments du tableau.