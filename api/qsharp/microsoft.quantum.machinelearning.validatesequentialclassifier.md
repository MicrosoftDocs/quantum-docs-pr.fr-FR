---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: Opération ValidateSequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706827"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="03f23-102">Opération ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="03f23-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="03f23-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="03f23-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="03f23-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03f23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03f23-105">Valide un classifieur séquentiel donné par rapport à un ensemble donné d’exemples préétiquetés.</span><span class="sxs-lookup"><span data-stu-id="03f23-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="03f23-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="03f23-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="03f23-107">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="03f23-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="03f23-108">Modèle séquentiel à valider.</span><span class="sxs-lookup"><span data-stu-id="03f23-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="03f23-109">exemples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="03f23-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="03f23-110">Exemples à utiliser pour valider le modèle donné.</span><span class="sxs-lookup"><span data-stu-id="03f23-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="03f23-111">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="03f23-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="03f23-112">Tolérance approximative à utiliser pour l’encodage de chaque échantillon comme entrée du classifieur séquentiel.</span><span class="sxs-lookup"><span data-stu-id="03f23-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="03f23-113">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03f23-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03f23-114">Nombre de mesures à utiliser pour classer chaque échantillon.</span><span class="sxs-lookup"><span data-stu-id="03f23-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="03f23-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="03f23-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="03f23-116">Planification selon laquelle les exemples doivent être dessinés à partir du jeu de validation.</span><span class="sxs-lookup"><span data-stu-id="03f23-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="03f23-117">Sortie : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="03f23-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="03f23-118">Résultats de la validation donnée.</span><span class="sxs-lookup"><span data-stu-id="03f23-118">The results of the given validation.</span></span>