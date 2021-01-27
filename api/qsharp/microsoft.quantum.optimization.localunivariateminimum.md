---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854613"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="99668-102">LocalUnivariateMinimum fonction)</span><span class="sxs-lookup"><span data-stu-id="99668-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="99668-103">Espace de noms : [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="99668-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="99668-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99668-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99668-105">Retourne la valeur minimale locale pour une fonction Student sur un intervalle délimité, à l’aide d’une recherche d’intervalle d’or.</span><span class="sxs-lookup"><span data-stu-id="99668-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="99668-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="99668-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="99668-107">FN : [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="99668-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="99668-108">Fonction Student à réduire.</span><span class="sxs-lookup"><span data-stu-id="99668-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="99668-109">limites : ([double](xref:microsoft.quantum.lang-ref.double),[double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="99668-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="99668-110">Intervalle dans lequel la valeur minimale locale doit être recherchée.</span><span class="sxs-lookup"><span data-stu-id="99668-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="99668-111">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="99668-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="99668-112">Précision de l’entrée de la fonction à tolérer.</span><span class="sxs-lookup"><span data-stu-id="99668-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="99668-113">La recherche des Optima locaux se poursuivra jusqu’à ce que la largeur de l’intervalle soit inférieure à celle de cette tolérance.</span><span class="sxs-lookup"><span data-stu-id="99668-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="99668-114">Sortie : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="99668-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="99668-115">Optima local de la fonction donnée, situé dans les limites spécifiées.</span><span class="sxs-lookup"><span data-stu-id="99668-115">A local optima of the given function, located within the given bounds.</span></span>