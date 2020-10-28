---
uid: Microsoft.Quantum.Canon.Angle
title: Fonction angle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705523"
---
# <a name="angle-function"></a>Fonction angle

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


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

