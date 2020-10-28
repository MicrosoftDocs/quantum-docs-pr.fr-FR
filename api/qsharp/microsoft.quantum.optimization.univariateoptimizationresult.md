---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Type défini par l’utilisateur UnivariateOptimizationResult
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708789"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="0c068-102">Type défini par l’utilisateur UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="0c068-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="0c068-103">Espace de noms : [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="0c068-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="0c068-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c068-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c068-105">Représente le résultat de l’optimisation d’une fonction Student.</span><span class="sxs-lookup"><span data-stu-id="0c068-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="0c068-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="0c068-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="0c068-107">Coordonnée : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0c068-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0c068-108">Entrée à laquelle une optimale a été trouvée.</span><span class="sxs-lookup"><span data-stu-id="0c068-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="0c068-109">Valeur : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0c068-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0c068-110">Valeur retournée par la fonction à son niveau optimal.</span><span class="sxs-lookup"><span data-stu-id="0c068-110">Value returned by the function at its optimum.</span></span>