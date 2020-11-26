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
# <a name="message-function"></a><span data-ttu-id="be7be-102">Message, fonction</span><span class="sxs-lookup"><span data-stu-id="be7be-102">Message function</span></span>

<span data-ttu-id="be7be-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="be7be-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="be7be-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="be7be-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="be7be-105">Consigne un message.</span><span class="sxs-lookup"><span data-stu-id="be7be-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="be7be-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="be7be-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="be7be-107">MSG : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="be7be-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="be7be-108">Message à signaler.</span><span class="sxs-lookup"><span data-stu-id="be7be-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be7be-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be7be-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="be7be-110">Notes</span><span class="sxs-lookup"><span data-stu-id="be7be-110">Remarks</span></span>

<span data-ttu-id="be7be-111">Le comportement spécifique de cette fonction est dépendant du simulateur, mais dans la plupart des cas, le message indiqué est écrit dans la console.</span><span class="sxs-lookup"><span data-stu-id="be7be-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>