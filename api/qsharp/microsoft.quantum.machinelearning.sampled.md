---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Fonction échantillonnée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854945"
---
# <a name="sampled-function"></a><span data-ttu-id="07761-102">Fonction échantillonnée</span><span class="sxs-lookup"><span data-stu-id="07761-102">Sampled function</span></span>

<span data-ttu-id="07761-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="07761-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="07761-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="07761-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="07761-105">Échantillonne un tableau donné, à l’aide de la planification donnée.</span><span class="sxs-lookup"><span data-stu-id="07761-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="07761-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="07761-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="07761-107">planification : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="07761-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="07761-108">Planification à utiliser dans les valeurs d’échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="07761-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="07761-109">valeurs : 't []</span><span class="sxs-lookup"><span data-stu-id="07761-109">values : 'T[]</span></span>

<span data-ttu-id="07761-110">Tableau de valeurs à échantillonner.</span><span class="sxs-lookup"><span data-stu-id="07761-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="07761-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="07761-111">Output : 'T[]</span></span>

<span data-ttu-id="07761-112">Tableau d’éléments à partir de valeurs, suivant la planification donnée.</span><span class="sxs-lookup"><span data-stu-id="07761-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="07761-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="07761-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="07761-114">Peut</span><span class="sxs-lookup"><span data-stu-id="07761-114">'T</span></span>

