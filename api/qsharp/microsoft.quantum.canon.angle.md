---
uid: Microsoft.Quantum.Canon.Angle
title: Fonction angle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219411"
---
# <a name="angle-function"></a>Fonction angle

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne 1, si `index` a un nombre impair de 1s et-1, si `index` a un nombre pair de 1s.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Description

La valeur correspond au signe du coefficient du spectre Rademacher-Walsh de la variable n et de la fonction pour une affectation donnée qui détermine l’angle de la rotation.

## <a name="input"></a>Entrée

### <a name="index--int"></a>index : [int](xref:microsoft.quantum.lang-ref.int)

Assignation d’entrée en tant qu’entier (de 0 à 2 ^ n-1)



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

