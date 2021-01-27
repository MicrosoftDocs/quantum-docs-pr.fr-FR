---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: Opération ApplyCurriedOpC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: 65e861914b57cf8a32f2321f881248830b72c54e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841910"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="9a014-102">Opération ApplyCurriedOpC</span><span class="sxs-lookup"><span data-stu-id="9a014-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="9a014-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a014-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a014-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a014-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="9a014-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="9a014-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="9a014-106">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="9a014-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="9a014-107">tout d’abord :</span><span class="sxs-lookup"><span data-stu-id="9a014-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="9a014-108">deuxième : «U</span><span class="sxs-lookup"><span data-stu-id="9a014-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="9a014-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a014-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a014-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9a014-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a014-111">Peut</span><span class="sxs-lookup"><span data-stu-id="9a014-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="9a014-112">'U</span><span class="sxs-lookup"><span data-stu-id="9a014-112">'U</span></span>

