---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: Opération ApplyCurriedOpA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: 100d8a42d6475d3cdda349a2e685a6fbfff23cdc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845088"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="108bd-102">Opération ApplyCurriedOpA</span><span class="sxs-lookup"><span data-stu-id="108bd-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="108bd-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="108bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="108bd-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="108bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="108bd-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="108bd-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="108bd-106">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="108bd-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="108bd-107">tout d’abord :</span><span class="sxs-lookup"><span data-stu-id="108bd-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="108bd-108">deuxième : «U</span><span class="sxs-lookup"><span data-stu-id="108bd-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="108bd-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="108bd-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="108bd-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="108bd-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="108bd-111">Peut</span><span class="sxs-lookup"><span data-stu-id="108bd-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="108bd-112">'U</span><span class="sxs-lookup"><span data-stu-id="108bd-112">'U</span></span>

