---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 3b3ac3f9f8b70307099de60899c969abb2acad7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197668"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="a87bd-102">LessThanLexographic fonction)</span><span class="sxs-lookup"><span data-stu-id="a87bd-102">LessThanLexographic function</span></span>

<span data-ttu-id="a87bd-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a87bd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a87bd-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a87bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a87bd-105">Utilisé pour implémenter `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="a87bd-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="a87bd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a87bd-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="a87bd-107">Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a87bd-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="a87bd-108">gauche : 't []</span><span class="sxs-lookup"><span data-stu-id="a87bd-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="a87bd-109">Right : 't []</span><span class="sxs-lookup"><span data-stu-id="a87bd-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="a87bd-110">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a87bd-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a87bd-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a87bd-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a87bd-112">Peut</span><span class="sxs-lookup"><span data-stu-id="a87bd-112">'T</span></span>

