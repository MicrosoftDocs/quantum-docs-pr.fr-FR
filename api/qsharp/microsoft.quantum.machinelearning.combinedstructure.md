---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706875"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="ac772-102">CombinedStructure fonction)</span><span class="sxs-lookup"><span data-stu-id="ac772-102">CombinedStructure function</span></span>

<span data-ttu-id="ac772-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ac772-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ac772-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac772-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac772-105">À partir d’une ou plusieurs couches de rotations contrôlées, retourne une couche unique avec un index de paramètre de modèle décalé de telle sorte que des couches distinctes sont paramétrables par des paramètres de modèle distincts.</span><span class="sxs-lookup"><span data-stu-id="ac772-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="ac772-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ac772-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="ac772-107">couches : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="ac772-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="ac772-108">Couches à combiner.</span><span class="sxs-lookup"><span data-stu-id="ac772-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="ac772-109">Sortie : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="ac772-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="ac772-110">Couche unique de rotations contrôlées, représentant la concaténation de toutes les autres couches.</span><span class="sxs-lookup"><span data-stu-id="ac772-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>