---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: a506ccb637b331a392ea75383c8bd605114af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202938"
---
# <a name="rmencoding-function"></a><span data-ttu-id="e6755-102">RMEncoding fonction)</span><span class="sxs-lookup"><span data-stu-id="e6755-102">RMEncoding function</span></span>

<span data-ttu-id="e6755-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e6755-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e6755-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6755-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6755-105">{-1,1} codage d’une valeur de vérité booléenne</span><span class="sxs-lookup"><span data-stu-id="e6755-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="e6755-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e6755-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="e6755-107">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e6755-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e6755-108">Valeur booléenne</span><span class="sxs-lookup"><span data-stu-id="e6755-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="e6755-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e6755-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e6755-110">1, si `b` a la valeur false, sinon-1</span><span class="sxs-lookup"><span data-stu-id="e6755-110">1, if `b` is false, otherwise -1</span></span>