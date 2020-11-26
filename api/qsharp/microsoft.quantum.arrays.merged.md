---
uid: Microsoft.Quantum.Arrays.Merged
title: Fonction fusionnée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: b3383f8a04e6fa23562aa81e5b911d06752f4fb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220635"
---
# <a name="merged-function"></a><span data-ttu-id="7e8b3-102">Fonction fusionnée</span><span class="sxs-lookup"><span data-stu-id="7e8b3-102">Merged function</span></span>

<span data-ttu-id="7e8b3-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7e8b3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7e8b3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e8b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e8b3-105">À partir de deux tableaux triés, retourne un tableau unique contenant les éléments des deux en ordre trié.</span><span class="sxs-lookup"><span data-stu-id="7e8b3-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="7e8b3-106">Utilisé en interne par le tri de fusion.</span><span class="sxs-lookup"><span data-stu-id="7e8b3-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7e8b3-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="7e8b3-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="7e8b3-108">Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7e8b3-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="7e8b3-109">gauche : 't []</span><span class="sxs-lookup"><span data-stu-id="7e8b3-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="7e8b3-110">Right : 't []</span><span class="sxs-lookup"><span data-stu-id="7e8b3-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="7e8b3-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="7e8b3-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7e8b3-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7e8b3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7e8b3-113">Peut</span><span class="sxs-lookup"><span data-stu-id="7e8b3-113">'T</span></span>

