---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701917"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="5e8c8-102">LocalUnivariateMinimum fonction)</span><span class="sxs-lookup"><span data-stu-id="5e8c8-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="5e8c8-103">Espace de noms : [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="5e8c8-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="5e8c8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e8c8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e8c8-105">Retourne la valeur minimale locale pour une fonction Student sur un intervalle délimité, à l’aide d’une recherche d’intervalle d’or.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="5e8c8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="5e8c8-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="5e8c8-107">FN : [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e8c8-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e8c8-108">Fonction Student à réduire.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="5e8c8-109">limites : ([double](xref:microsoft.quantum.lang-ref.double),[double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="5e8c8-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="5e8c8-110">Intervalle dans lequel la valeur minimale locale doit être recherchée.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="5e8c8-111">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e8c8-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e8c8-112">Précision de l’entrée de la fonction à tolérer.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="5e8c8-113">La recherche des Optima locaux se poursuivra jusqu’à ce que la largeur de l’intervalle soit inférieure à celle de cette tolérance.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="5e8c8-114">Sortie : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="5e8c8-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="5e8c8-115">Optima local de la fonction donnée, situé dans les limites spécifiées.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-115">A local optima of the given function, located within the given bounds.</span></span>