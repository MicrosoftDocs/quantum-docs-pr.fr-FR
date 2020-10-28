---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702091"
---
# <a name="message-function"></a>Message, fonction

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


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