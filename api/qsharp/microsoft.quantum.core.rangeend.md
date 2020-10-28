---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702871"
---
# <a name="rangeend-function"></a>RangeEnd fonction)

Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Packages [](https://nuget.org/packages/)


Retourne la valeur de fin définie de la plage donnée, qui n’est pas nécessairement le dernier élément de la séquence.

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>Entrée

### <a name="range--range"></a>plage : [plage](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Valeur de fin définie de la plage donnée.

## <a name="remarks"></a>Notes

Le premier élément d’une expression de plage est `start` , son deuxième élément est `start+step` , le troisième élément est `start+step+step` , etc., jusqu’à ce que `end` soit passé.

Notez que la valeur de fin définie d’une plage peut être différente de celle du dernier élément de la séquence spécifiée par la plage ; par exemple, dans une plage 0.. 2.. 5 le dernier élément est 4, mais la valeur de fin est 5.