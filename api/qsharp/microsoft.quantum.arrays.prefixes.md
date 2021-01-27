---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Fonction Prefixes
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845508"
---
# <a name="prefixes-function"></a>Fonction Prefixes

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau, retourne tous ses préfixes.

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>Description

Retourne un tableau de tous les préfixes, en commençant par un tableau qui a uniquement le premier élément jusqu’au tableau complet.

## <a name="input"></a>Entrée

### <a name="array--t"></a>Tableau : 't []

Tableau d’éléments.



## <a name="output--t"></a>Sortie : 't [] []



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des `array` éléments.

## <a name="example"></a>Exemple

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```