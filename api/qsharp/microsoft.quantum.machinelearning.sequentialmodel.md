---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Type défini par l’utilisateur SequentialModel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196172"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="3838a-102">Type défini par l’utilisateur SequentialModel</span><span class="sxs-lookup"><span data-stu-id="3838a-102">SequentialModel user defined type</span></span>

<span data-ttu-id="3838a-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3838a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3838a-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3838a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3838a-105">Décrit un modèle de classifieur Quantum composé d’une séquence de rotations paramétrées et contrôlées, d’une assignation d’angles de rotation et d’un décalage entre les deux classes reconnues par le modèle.</span><span class="sxs-lookup"><span data-stu-id="3838a-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="3838a-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="3838a-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="3838a-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="3838a-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="3838a-108">Séquence de rotations contrôlées utilisées pour classer les entrées.</span><span class="sxs-lookup"><span data-stu-id="3838a-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="3838a-109">Paramètres : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3838a-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3838a-110">Assignation d’angles de rotation à la structure de classification donnée.</span><span class="sxs-lookup"><span data-stu-id="3838a-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="3838a-111">Biais : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3838a-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3838a-112">Décalage entre les deux classes reconnues par ce classifieur.</span><span class="sxs-lookup"><span data-stu-id="3838a-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="3838a-113">Références</span><span class="sxs-lookup"><span data-stu-id="3838a-113">References</span></span>

- [<span data-ttu-id="3838a-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="3838a-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)