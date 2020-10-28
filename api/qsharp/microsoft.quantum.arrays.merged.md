---
uid: Microsoft.Quantum.Arrays.Merged
title: Fonction fusionnée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705870"
---
# <a name="merged-function"></a><span data-ttu-id="2359e-102">Fonction fusionnée</span><span class="sxs-lookup"><span data-stu-id="2359e-102">Merged function</span></span>

<span data-ttu-id="2359e-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2359e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2359e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2359e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2359e-105">À partir de deux tableaux triés, retourne un tableau unique contenant les éléments des deux en ordre trié.</span><span class="sxs-lookup"><span data-stu-id="2359e-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="2359e-106">Utilisé en interne par le tri de fusion.</span><span class="sxs-lookup"><span data-stu-id="2359e-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2359e-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="2359e-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="2359e-108">Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2359e-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="2359e-109">gauche : 't []</span><span class="sxs-lookup"><span data-stu-id="2359e-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="2359e-110">Right : 't []</span><span class="sxs-lookup"><span data-stu-id="2359e-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="2359e-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="2359e-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2359e-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2359e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2359e-113">Peut</span><span class="sxs-lookup"><span data-stu-id="2359e-113">'T</span></span>

