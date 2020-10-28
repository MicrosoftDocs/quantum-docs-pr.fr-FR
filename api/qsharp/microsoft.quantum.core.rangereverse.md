---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702865"
---
# <a name="rangereverse-function"></a>RangeReverse fonction)

Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Packages [](https://nuget.org/packages/)


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