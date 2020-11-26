---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211965"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="5278d-102">CombinedStructure fonction)</span><span class="sxs-lookup"><span data-stu-id="5278d-102">CombinedStructure function</span></span>

<span data-ttu-id="5278d-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5278d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5278d-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5278d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="5278d-105">À partir d’une ou plusieurs couches de rotations contrôlées, retourne une couche unique avec un index de paramètre de modèle décalé de telle sorte que des couches distinctes sont paramétrables par des paramètres de modèle distincts.</span><span class="sxs-lookup"><span data-stu-id="5278d-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="5278d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="5278d-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="5278d-107">couches : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="5278d-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="5278d-108">Couches à combiner.</span><span class="sxs-lookup"><span data-stu-id="5278d-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="5278d-109">Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="5278d-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="5278d-110">Couche unique de rotations contrôlées, représentant la concaténation de toutes les autres couches.</span><span class="sxs-lookup"><span data-stu-id="5278d-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>