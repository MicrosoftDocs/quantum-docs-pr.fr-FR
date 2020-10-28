---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingStep
title: Opération de _RunSingleTrainingStep
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingStep
qsharp.summary: attempts a single parameter update in the direction of mini batch gradient
ms.openlocfilehash: c40bf6f1ceecef2cb196846b4f5a1c49023f1f74
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706947"
---
# <a name="_runsingletrainingstep-operation"></a><span data-ttu-id="2453e-102">Opération de _RunSingleTrainingStep</span><span class="sxs-lookup"><span data-stu-id="2453e-102">_RunSingleTrainingStep operation</span></span>

<span data-ttu-id="2453e-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2453e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2453e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2453e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2453e-105">tente une mise à jour de paramètre unique dans le sens du dégradé de mini-lot</span><span class="sxs-lookup"><span data-stu-id="2453e-105">attempts a single parameter update in the direction of mini batch gradient</span></span>

```qsharp
operation _RunSingleTrainingStep (miniBatch : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel) : (Double, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="2453e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2453e-106">Input</span></span>

### <a name="minibatch--labeledsamplestategenerator"></a><span data-ttu-id="2453e-107">minilot : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="2453e-107">miniBatch : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>

<span data-ttu-id="2453e-108">conteneur d’exemples étiquetés dans le mini-lot</span><span class="sxs-lookup"><span data-stu-id="2453e-108">container of labeled samples in the mini batch</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="2453e-109">Options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="2453e-109">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>




### <a name="model--sequentialmodel"></a><span data-ttu-id="2453e-110">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="2453e-110">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--doublesequentialmodel"></a><span data-ttu-id="2453e-111">Sortie : ([double](xref:microsoft.quantum.lang-ref.double),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="2453e-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

<span data-ttu-id="2453e-112">paire (utilitaire, (nouveau) paramètres)</span><span class="sxs-lookup"><span data-stu-id="2453e-112">(utility, (new)parameters) pair</span></span>