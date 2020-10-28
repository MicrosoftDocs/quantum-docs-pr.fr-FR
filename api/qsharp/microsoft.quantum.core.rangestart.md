---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702838"
---
# <a name="rangestart-function"></a>RangeStart, fonction

Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Packages [](https://nuget.org/packages/)


Retourne la valeur de début définie de la plage donnée.

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>Entrée

### <a name="range--range"></a>plage : [plage](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Valeur de début définie de la plage donnée.

## <a name="remarks"></a>Notes

Le premier élément d’une expression de plage est `start` , son deuxième élément est `start+step` , le troisième élément est `start+step+step` , etc., jusqu’à ce que `end` soit passé.

Notez que la valeur de début définie d’une plage est identique à celle du premier élément de la séquence, à moins que la plage spécifie une séquence vide (par exemple, 2. 1).