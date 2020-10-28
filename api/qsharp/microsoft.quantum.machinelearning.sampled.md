---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Fonction échantillonnée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707976"
---
# <a name="sampled-function"></a><span data-ttu-id="61036-102">Fonction échantillonnée</span><span class="sxs-lookup"><span data-stu-id="61036-102">Sampled function</span></span>

<span data-ttu-id="61036-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="61036-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="61036-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="61036-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="61036-105">Échantillonne un tableau donné, à l’aide de la planification donnée.</span><span class="sxs-lookup"><span data-stu-id="61036-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="61036-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="61036-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="61036-107">planification : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="61036-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="61036-108">Planification à utiliser dans les valeurs d’échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="61036-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="61036-109">valeurs : 't []</span><span class="sxs-lookup"><span data-stu-id="61036-109">values : 'T[]</span></span>

<span data-ttu-id="61036-110">Tableau de valeurs à échantillonner.</span><span class="sxs-lookup"><span data-stu-id="61036-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="61036-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="61036-111">Output : 'T[]</span></span>

<span data-ttu-id="61036-112">Tableau d’éléments à partir de valeurs, suivant la planification donnée.</span><span class="sxs-lookup"><span data-stu-id="61036-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="61036-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="61036-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61036-114">Peut</span><span class="sxs-lookup"><span data-stu-id="61036-114">'T</span></span>

