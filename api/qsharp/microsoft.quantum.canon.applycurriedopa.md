---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: Opération ApplyCurriedOpA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: 2b0f86efe79654e1f886f0ccd0287e07225cbf83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705419"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="4e895-102">Opération ApplyCurriedOpA</span><span class="sxs-lookup"><span data-stu-id="4e895-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="4e895-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4e895-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4e895-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e895-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="4e895-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="4e895-105">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="4e895-106">curriedOp : > 'U => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e895-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="4e895-107">tout d’abord :</span><span class="sxs-lookup"><span data-stu-id="4e895-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="4e895-108">deuxième : «U</span><span class="sxs-lookup"><span data-stu-id="4e895-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="4e895-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e895-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4e895-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4e895-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e895-111">Peut</span><span class="sxs-lookup"><span data-stu-id="4e895-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="4e895-112">'U</span><span class="sxs-lookup"><span data-stu-id="4e895-112">'U</span></span>
