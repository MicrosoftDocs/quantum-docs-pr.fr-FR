---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Type défini par l’utilisateur UnivariateOptimizationResult
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854567"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="2f0b8-102">Type défini par l’utilisateur UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="2f0b8-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="2f0b8-103">Espace de noms : [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="2f0b8-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="2f0b8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f0b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f0b8-105">Représente le résultat de l’optimisation d’une fonction Student.</span><span class="sxs-lookup"><span data-stu-id="2f0b8-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="2f0b8-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="2f0b8-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="2f0b8-107">Coordonnée : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2f0b8-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2f0b8-108">Entrée à laquelle une optimale a été trouvée.</span><span class="sxs-lookup"><span data-stu-id="2f0b8-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="2f0b8-109">Valeur : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2f0b8-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2f0b8-110">Valeur retournée par la fonction à son niveau optimal.</span><span class="sxs-lookup"><span data-stu-id="2f0b8-110">Value returned by the function at its optimum.</span></span>