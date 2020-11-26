---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 90a9e31bf5c4a5e92a35998ddaec8c9e9de9888e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224035"
---
# <a name="rangeend-function"></a>RangeEnd fonction)

Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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