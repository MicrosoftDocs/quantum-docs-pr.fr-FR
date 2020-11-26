---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: Opération ApplyCurriedOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: ab652159fa64a95401d07998ed4aaae5c4dbb92e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219020"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="48f41-102">Opération ApplyCurriedOp</span><span class="sxs-lookup"><span data-stu-id="48f41-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="48f41-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="48f41-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="48f41-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48f41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="48f41-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="48f41-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="48f41-106">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48f41-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="48f41-107">tout d’abord :</span><span class="sxs-lookup"><span data-stu-id="48f41-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="48f41-108">deuxième : «U</span><span class="sxs-lookup"><span data-stu-id="48f41-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="48f41-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48f41-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="48f41-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="48f41-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48f41-111">Peut</span><span class="sxs-lookup"><span data-stu-id="48f41-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="48f41-112">'U</span><span class="sxs-lookup"><span data-stu-id="48f41-112">'U</span></span>

