---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Type défini par l’utilisateur SequentialModel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707961"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="433a8-102">Type défini par l’utilisateur SequentialModel</span><span class="sxs-lookup"><span data-stu-id="433a8-102">SequentialModel user defined type</span></span>

<span data-ttu-id="433a8-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="433a8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="433a8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="433a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="433a8-105">Décrit un modèle de classifieur Quantum composé d’une séquence de rotations paramétrées et contrôlées, d’une assignation d’angles de rotation et d’un décalage entre les deux classes reconnues par le modèle.</span><span class="sxs-lookup"><span data-stu-id="433a8-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="433a8-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="433a8-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="433a8-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="433a8-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="433a8-108">Séquence de rotations contrôlées utilisées pour classer les entrées.</span><span class="sxs-lookup"><span data-stu-id="433a8-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="433a8-109">Paramètres : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="433a8-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="433a8-110">Assignation d’angles de rotation à la structure de classification donnée.</span><span class="sxs-lookup"><span data-stu-id="433a8-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="433a8-111">Biais : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="433a8-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="433a8-112">Décalage entre les deux classes reconnues par ce classifieur.</span><span class="sxs-lookup"><span data-stu-id="433a8-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="433a8-113">Références</span><span class="sxs-lookup"><span data-stu-id="433a8-113">References</span></span>

- [<span data-ttu-id="433a8-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="433a8-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)