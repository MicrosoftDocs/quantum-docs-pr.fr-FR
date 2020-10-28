---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: Opération ApplyCurriedOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: 22e2ace51175ed9df1c70bf75ce2b497f8449020
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705422"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="2530e-102">Opération ApplyCurriedOp</span><span class="sxs-lookup"><span data-stu-id="2530e-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="2530e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2530e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2530e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2530e-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="2530e-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="2530e-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="2530e-106">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2530e-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="2530e-107">tout d’abord :</span><span class="sxs-lookup"><span data-stu-id="2530e-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="2530e-108">deuxième : «U</span><span class="sxs-lookup"><span data-stu-id="2530e-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="2530e-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2530e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2530e-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2530e-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2530e-111">Peut</span><span class="sxs-lookup"><span data-stu-id="2530e-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="2530e-112">'U</span><span class="sxs-lookup"><span data-stu-id="2530e-112">'U</span></span>

