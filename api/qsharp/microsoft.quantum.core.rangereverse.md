---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853661"
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