---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856007"
---
# <a name="defaulttrainingoptions-function"></a><span data-ttu-id="1bb31-102">DefaultTrainingOptions fonction)</span><span class="sxs-lookup"><span data-stu-id="1bb31-102">DefaultTrainingOptions function</span></span>

<span data-ttu-id="1bb31-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1bb31-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1bb31-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1bb31-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="1bb31-105">Retourne un jeu d’options par défaut pour les classifieurs d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="1bb31-105">Returns a default set of options for training classifiers.</span></span>

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a><span data-ttu-id="1bb31-106">Sortie : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="1bb31-106">Output : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="1bb31-107">Un ensemble raisonnable d’options de formation par défaut à utiliser lors de l’apprentissage des classifieurs.</span><span class="sxs-lookup"><span data-stu-id="1bb31-107">A reasonable set of default training options for use when training classifiers.</span></span>

## <a name="example"></a><span data-ttu-id="1bb31-108">Exemple</span><span class="sxs-lookup"><span data-stu-id="1bb31-108">Example</span></span>

<span data-ttu-id="1bb31-109">Pour utiliser les options par défaut, mais avec des mesures supplémentaires, utilisez l' `w/` opérateur :</span><span class="sxs-lookup"><span data-stu-id="1bb31-109">To use the default options, but with additional measurements, use the `w/` operator:</span></span>

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```