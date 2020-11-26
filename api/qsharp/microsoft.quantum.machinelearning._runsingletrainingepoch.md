---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: Opération de _RunSingleTrainingEpoch
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 71780645a025972f11f32f8ba8fd94d098604f9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196750"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="aa678-102">Opération de _RunSingleTrainingEpoch</span><span class="sxs-lookup"><span data-stu-id="aa678-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="aa678-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="aa678-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="aa678-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="aa678-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="aa678-105">Effectuez une époque de formation de classifieur séquentiel sur un sous-ensemble d’exemples de données.</span><span class="sxs-lookup"><span data-stu-id="aa678-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="aa678-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="aa678-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="aa678-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="aa678-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="aa678-108">planification : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="aa678-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="aa678-109">periodScore : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aa678-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aa678-110">Nombre d’étapes de dégradé à effectuer entre les points de notation.</span><span class="sxs-lookup"><span data-stu-id="aa678-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="aa678-111">Pour une meilleure précision, définissez sur 1.</span><span class="sxs-lookup"><span data-stu-id="aa678-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="aa678-112">Options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="aa678-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="aa678-113">Options à utiliser pour l’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="aa678-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="aa678-114">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="aa678-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="aa678-115">Modèle séquentiel à former.</span><span class="sxs-lookup"><span data-stu-id="aa678-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="aa678-116">nPreviousBestMisses : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aa678-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aa678-117">Le meilleur nombre de classifications incorrectes observées dans les époques précédentes.</span><span class="sxs-lookup"><span data-stu-id="aa678-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="aa678-118">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="aa678-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="aa678-119">Plus petit nombre de classifications incorrectes observées par le biais de cette époque.</span><span class="sxs-lookup"><span data-stu-id="aa678-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="aa678-120">Le nouveau modèle séquentiel le plus approprié a été trouvé.</span><span class="sxs-lookup"><span data-stu-id="aa678-120">The new best sequential model found.</span></span>