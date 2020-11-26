---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Fonction Prefixes
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220384"
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