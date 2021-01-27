---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Opération MaybeChooseElement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856113"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="4df18-102">Opération MaybeChooseElement</span><span class="sxs-lookup"><span data-stu-id="4df18-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="4df18-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="4df18-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="4df18-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4df18-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4df18-105">À partir d’un tableau de données et d’une distribution sur ses index, tente de choisir un élément au hasard.</span><span class="sxs-lookup"><span data-stu-id="4df18-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="4df18-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4df18-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="4df18-107">données : 't []</span><span class="sxs-lookup"><span data-stu-id="4df18-107">data : 'T[]</span></span>

<span data-ttu-id="4df18-108">Tableau à partir duquel un élément doit être choisi.</span><span class="sxs-lookup"><span data-stu-id="4df18-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="4df18-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="4df18-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="4df18-110">Distribution sur les index de `data` .</span><span class="sxs-lookup"><span data-stu-id="4df18-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="4df18-111">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="4df18-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4df18-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4df18-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4df18-113">Peut</span><span class="sxs-lookup"><span data-stu-id="4df18-113">'T</span></span>



## <a name="example"></a><span data-ttu-id="4df18-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="4df18-114">Example</span></span>

<span data-ttu-id="4df18-115">L’extrait de code Q # suivant choisit un élément aléatoire dans un tableau :</span><span class="sxs-lookup"><span data-stu-id="4df18-115">The following Q# snippet chooses an element at random from an array:</span></span>

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```