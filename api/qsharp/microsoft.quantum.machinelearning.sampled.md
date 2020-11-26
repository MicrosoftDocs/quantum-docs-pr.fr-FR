---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Fonction échantillonnée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211625"
---
# <a name="sampled-function"></a><span data-ttu-id="b7e4f-102">Fonction échantillonnée</span><span class="sxs-lookup"><span data-stu-id="b7e4f-102">Sampled function</span></span>

<span data-ttu-id="b7e4f-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b7e4f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b7e4f-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b7e4f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b7e4f-105">Échantillonne un tableau donné, à l’aide de la planification donnée.</span><span class="sxs-lookup"><span data-stu-id="b7e4f-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b7e4f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b7e4f-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="b7e4f-107">planification : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="b7e4f-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="b7e4f-108">Planification à utiliser dans les valeurs d’échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="b7e4f-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="b7e4f-109">valeurs : 't []</span><span class="sxs-lookup"><span data-stu-id="b7e4f-109">values : 'T[]</span></span>

<span data-ttu-id="b7e4f-110">Tableau de valeurs à échantillonner.</span><span class="sxs-lookup"><span data-stu-id="b7e4f-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="b7e4f-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="b7e4f-111">Output : 'T[]</span></span>

<span data-ttu-id="b7e4f-112">Tableau d’éléments à partir de valeurs, suivant la planification donnée.</span><span class="sxs-lookup"><span data-stu-id="b7e4f-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b7e4f-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b7e4f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b7e4f-114">Peut</span><span class="sxs-lookup"><span data-stu-id="b7e4f-114">'T</span></span>

