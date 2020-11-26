---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199010"
---
# <a name="message-function"></a>Message, fonction

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Consigne un message.

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>Entrée

### <a name="msg--string"></a>MSG : [chaîne](xref:microsoft.quantum.lang-ref.string)

Message à signaler.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Le comportement spécifique de cette fonction est dépendant du simulateur, mais dans la plupart des cas, le message indiqué est écrit dans la console.