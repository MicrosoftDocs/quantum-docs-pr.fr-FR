---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: Opération TrainSequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 12c4df59941b682d9de798e6585b59d1c34924dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702040"
---
# <a name="trainsequentialclassifier-operation"></a><span data-ttu-id="6dbbe-102">Opération TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="6dbbe-102">TrainSequentialClassifier operation</span></span>

<span data-ttu-id="6dbbe-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6dbbe-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6dbbe-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6dbbe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6dbbe-105">Étant donné la structure d’un classifieur séquentiel, forme le classifieur sur un jeu d’apprentissage étiqueté donné.</span><span class="sxs-lookup"><span data-stu-id="6dbbe-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set.</span></span>

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="6dbbe-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6dbbe-106">Input</span></span>

### <a name="models--sequentialmodel"></a><span data-ttu-id="6dbbe-107">modèles : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span><span class="sxs-lookup"><span data-stu-id="6dbbe-107">models : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span></span>

<span data-ttu-id="6dbbe-108">Tableau de modèles à utiliser comme points de départ pendant l’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="6dbbe-108">An array of models to be used as starting points during training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="6dbbe-109">exemples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="6dbbe-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="6dbbe-110">Ensemble de données d’apprentissage étiquetées qui seront utilisées pour effectuer l’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="6dbbe-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="6dbbe-111">Options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="6dbbe-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="6dbbe-112">Configuration à utiliser lors de la formation ; @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" pour plus d’informations, consultez et.</span><span class="sxs-lookup"><span data-stu-id="6dbbe-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="6dbbe-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="6dbbe-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="6dbbe-114">Une planification d’échantillonnage à utiliser lors de la sélection d’exemples à partir des données d’apprentissage pendant les étapes de formation.</span><span class="sxs-lookup"><span data-stu-id="6dbbe-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="6dbbe-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="6dbbe-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="6dbbe-116">Une planification d’échantillonnage à utiliser lors de la sélection d’exemples à partir des données d’apprentissage lors de la sélection du point de départ qui a entraîné le meilleur score de classifieur.</span><span class="sxs-lookup"><span data-stu-id="6dbbe-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="6dbbe-117">Sortie : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="6dbbe-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="6dbbe-118">Paramétrage du classifieur donné et d’un décalage entre les deux classes, qui correspond au meilleur résultat de chacun des points de départ donnés.</span><span class="sxs-lookup"><span data-stu-id="6dbbe-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="6dbbe-119">Nombre d’échecs observés au meilleur modèle de classifieur.</span><span class="sxs-lookup"><span data-stu-id="6dbbe-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dbbe-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6dbbe-120">See Also</span></span>

- [<span data-ttu-id="6dbbe-121">Microsoft. Quantum. MachineLearning. TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="6dbbe-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [<span data-ttu-id="6dbbe-122">Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="6dbbe-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)