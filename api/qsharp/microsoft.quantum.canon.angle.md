---
uid: Microsoft.Quantum.Canon.Angle
title: Fonction angle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842052"
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

