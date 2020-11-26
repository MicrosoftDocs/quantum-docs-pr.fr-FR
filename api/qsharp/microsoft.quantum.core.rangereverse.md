---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213835"
---
# <a name="rangereverse-function"></a>RangeReverse fonction)

Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Retourne une nouvelle plage qui est l’inverse de la plage d’entrée.

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>Entrée

### <a name="r--range"></a>r : [plage](xref:microsoft.quantum.lang-ref.range)

Plage d’entrée.



## <a name="output--range"></a>Sortie : [plage](xref:microsoft.quantum.lang-ref.range)

Nouvelle plage qui est l’inverse de la plage donnée.

## <a name="remarks"></a>Notes

Notez que l’inverse d’une plage n’est pas tout simplement `end` .. `-step` .. `start` , car le dernier élément réel d’une plage ne peut pas être le même que `end` .