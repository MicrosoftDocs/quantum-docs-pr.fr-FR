---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Type défini par l’utilisateur TrainingOptions
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 280a3857aa7bc42f636a33f893d4f450e79b6a6a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196121"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="b0698-102">Type défini par l’utilisateur TrainingOptions</span><span class="sxs-lookup"><span data-stu-id="b0698-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="b0698-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b0698-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b0698-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b0698-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b0698-105">Collection d’options à utiliser pour l’apprentissage des classifieurs Quantum.</span><span class="sxs-lookup"><span data-stu-id="b0698-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="b0698-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="b0698-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="b0698-107">LearningRate : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b0698-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b0698-108">Taux d’apprentissage par lequel les dégradés doivent être mis à l’échelle lors de la mise à jour des paramètres de modèle pendant les étapes d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="b0698-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="b0698-109">Tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b0698-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b0698-110">Tolérance approximative à utiliser lors de la préparation des exemples en tant qu’États quantiques.</span><span class="sxs-lookup"><span data-stu-id="b0698-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="b0698-111">MinibatchSize : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0698-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0698-112">Nombre d’échantillons à utiliser dans chaque minilot d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="b0698-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="b0698-113">NMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0698-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0698-114">Nombre de fois où chaque résultat de la classification doit être mesuré afin d’estimer la probabilité de la classification.</span><span class="sxs-lookup"><span data-stu-id="b0698-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="b0698-115">MaxEpochs : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0698-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0698-116">Nombre maximal d’époques pour l’apprentissage de chaque modèle.</span><span class="sxs-lookup"><span data-stu-id="b0698-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="b0698-117">MaxStalls : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0698-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0698-118">Nombre maximal de fois où une époque d’apprentissage est autorisée à se bloquer (à peu près zéro gradient) avant d’échouer.</span><span class="sxs-lookup"><span data-stu-id="b0698-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="b0698-119">StochasticRescaleFactor : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b0698-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b0698-120">Valeur de redimensionnement des modèles bloqués par avant une nouvelle tentative de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="b0698-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="b0698-121">ScoringPeriod : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0698-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0698-122">Nombre d’étapes de dégradé à effectuer entre les points de notation.</span><span class="sxs-lookup"><span data-stu-id="b0698-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="b0698-123">Pour une meilleure précision, définissez sur 1.</span><span class="sxs-lookup"><span data-stu-id="b0698-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="b0698-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [unité](xref:microsoft.quantum.lang-ref.unit) de chaîne</span><span class="sxs-lookup"><span data-stu-id="b0698-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="b0698-125">Fonction qui peut être utilisée pour fournir des commentaires détaillés.</span><span class="sxs-lookup"><span data-stu-id="b0698-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0698-126">Notes</span><span class="sxs-lookup"><span data-stu-id="b0698-126">Remarks</span></span>

<span data-ttu-id="b0698-127">Ce type défini par l’utilisateur ne doit pas être créé directement, mais il doit être spécifié en appelant @"microsoft.quantum.machinelearning.defaulttrainingoptions" , puis en utilisant l' `w/` opérateur pour remplacer des valeurs par défaut différentes.</span><span class="sxs-lookup"><span data-stu-id="b0698-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="b0698-128">Par exemple, pour utiliser les mesures 100 000 et au plus 8 époques de formation :</span><span class="sxs-lookup"><span data-stu-id="b0698-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="b0698-129">Références</span><span class="sxs-lookup"><span data-stu-id="b0698-129">References</span></span>

- [<span data-ttu-id="b0698-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="b0698-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)