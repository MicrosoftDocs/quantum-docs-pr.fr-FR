---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Type défini par l’utilisateur SequentialModel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854897"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="61106-102">Type défini par l’utilisateur SequentialModel</span><span class="sxs-lookup"><span data-stu-id="61106-102">SequentialModel user defined type</span></span>

<span data-ttu-id="61106-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="61106-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="61106-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="61106-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="61106-105">Décrit un modèle de classifieur Quantum composé d’une séquence de rotations paramétrées et contrôlées, d’une assignation d’angles de rotation et d’un décalage entre les deux classes reconnues par le modèle.</span><span class="sxs-lookup"><span data-stu-id="61106-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="61106-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="61106-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="61106-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="61106-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="61106-108">Séquence de rotations contrôlées utilisées pour classer les entrées.</span><span class="sxs-lookup"><span data-stu-id="61106-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="61106-109">Paramètres : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="61106-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="61106-110">Assignation d’angles de rotation à la structure de classification donnée.</span><span class="sxs-lookup"><span data-stu-id="61106-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="61106-111">Biais : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="61106-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="61106-112">Décalage entre les deux classes reconnues par ce classifieur.</span><span class="sxs-lookup"><span data-stu-id="61106-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="61106-113">Références</span><span class="sxs-lookup"><span data-stu-id="61106-113">References</span></span>

- [<span data-ttu-id="61106-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="61106-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)