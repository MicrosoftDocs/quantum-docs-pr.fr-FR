---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: Opération ApplyCurriedOpA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: db3f63cbe2ee5ef048c7e378864d68696f55331f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218952"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="1bc39-102">Opération ApplyCurriedOpA</span><span class="sxs-lookup"><span data-stu-id="1bc39-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="1bc39-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1bc39-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1bc39-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1bc39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="1bc39-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="1bc39-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="1bc39-106">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="1bc39-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="1bc39-107">tout d’abord :</span><span class="sxs-lookup"><span data-stu-id="1bc39-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="1bc39-108">deuxième : «U</span><span class="sxs-lookup"><span data-stu-id="1bc39-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="1bc39-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1bc39-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1bc39-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1bc39-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1bc39-111">Peut</span><span class="sxs-lookup"><span data-stu-id="1bc39-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="1bc39-112">'U</span><span class="sxs-lookup"><span data-stu-id="1bc39-112">'U</span></span>

