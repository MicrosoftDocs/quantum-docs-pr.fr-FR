---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Type défini par l’utilisateur UnivariateOptimizationResult
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194030"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="e3369-102">Type défini par l’utilisateur UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="e3369-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="e3369-103">Espace de noms : [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="e3369-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="e3369-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3369-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3369-105">Représente le résultat de l’optimisation d’une fonction Student.</span><span class="sxs-lookup"><span data-stu-id="e3369-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="e3369-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="e3369-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="e3369-107">Coordonnée : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e3369-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e3369-108">Entrée à laquelle une optimale a été trouvée.</span><span class="sxs-lookup"><span data-stu-id="e3369-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="e3369-109">Valeur : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e3369-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e3369-110">Valeur retournée par la fonction à son niveau optimal.</span><span class="sxs-lookup"><span data-stu-id="e3369-110">Value returned by the function at its optimum.</span></span>