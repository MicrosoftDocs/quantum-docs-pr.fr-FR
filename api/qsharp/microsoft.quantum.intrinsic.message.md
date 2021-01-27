---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849377"
---
# <a name="message-function"></a><span data-ttu-id="11b59-102">Message, fonction</span><span class="sxs-lookup"><span data-stu-id="11b59-102">Message function</span></span>

<span data-ttu-id="11b59-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="11b59-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="11b59-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="11b59-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="11b59-105">Consigne un message.</span><span class="sxs-lookup"><span data-stu-id="11b59-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="11b59-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="11b59-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="11b59-107">MSG : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="11b59-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="11b59-108">Message à signaler.</span><span class="sxs-lookup"><span data-stu-id="11b59-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="11b59-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11b59-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="11b59-110">Notes</span><span class="sxs-lookup"><span data-stu-id="11b59-110">Remarks</span></span>

<span data-ttu-id="11b59-111">Le comportement spécifique de cette fonction est dépendant du simulateur, mais dans la plupart des cas, le message indiqué est écrit dans la console.</span><span class="sxs-lookup"><span data-stu-id="11b59-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>