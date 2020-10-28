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
# <a name="message-function"></a><span data-ttu-id="de599-102">Message, fonction</span><span class="sxs-lookup"><span data-stu-id="de599-102">Message function</span></span>

<span data-ttu-id="de599-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="de599-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="de599-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de599-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de599-105">Consigne un message.</span><span class="sxs-lookup"><span data-stu-id="de599-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="de599-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="de599-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="de599-107">MSG : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="de599-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="de599-108">Message à signaler.</span><span class="sxs-lookup"><span data-stu-id="de599-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de599-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de599-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="de599-110">Notes</span><span class="sxs-lookup"><span data-stu-id="de599-110">Remarks</span></span>

<span data-ttu-id="de599-111">Le comportement spécifique de cette fonction est dépendant du simulateur, mais dans la plupart des cas, le message indiqué est écrit dans la console.</span><span class="sxs-lookup"><span data-stu-id="de599-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>