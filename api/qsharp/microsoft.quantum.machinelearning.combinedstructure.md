---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: b8ec007202c8e63dc2e98d0c752f6ba1a453e236
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847416"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="04ea6-102">CombinedStructure fonction)</span><span class="sxs-lookup"><span data-stu-id="04ea6-102">CombinedStructure function</span></span>

<span data-ttu-id="04ea6-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="04ea6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="04ea6-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="04ea6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="04ea6-105">À partir d’une ou plusieurs couches de rotations contrôlées, retourne une couche unique avec un index de paramètre de modèle décalé de telle sorte que des couches distinctes sont paramétrables par des paramètres de modèle distincts.</span><span class="sxs-lookup"><span data-stu-id="04ea6-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="04ea6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="04ea6-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="04ea6-107">couches : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="04ea6-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="04ea6-108">Couches à combiner.</span><span class="sxs-lookup"><span data-stu-id="04ea6-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="04ea6-109">Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="04ea6-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="04ea6-110">Couche unique de rotations contrôlées, représentant la concaténation de toutes les autres couches.</span><span class="sxs-lookup"><span data-stu-id="04ea6-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>

## <a name="example"></a><span data-ttu-id="04ea6-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="04ea6-111">Example</span></span>

<span data-ttu-id="04ea6-112">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="04ea6-112">The following are equivalent:</span></span>

```qsharp
let structure = CombinedStructure([
    LocalRotationLayer(2, PauliY),
    CyclicEntanglingLayer(3, PauliX, 2)
]);
let structure = [
    ControlledRotation((0, new Int[0]), PauliY, 0),
    ControlledRotation((1, new Int[0]), PauliY, 1),
    ControlledRotation((0, [2]), PauliX, 2),
    ControlledRotation((1, [0]), PauliX, 3),
    ControlledRotation((2, [1]), PauliX, 4)
];
```