---
uid: Microsoft.Quantum.Arrays.Most
title: La plupart des fonctions
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845577"
---
# <a name="most-function"></a>La plupart des fonctions

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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