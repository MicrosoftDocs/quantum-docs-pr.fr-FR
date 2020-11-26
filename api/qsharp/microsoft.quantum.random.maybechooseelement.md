---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Opération MaybeChooseElement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192857"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="deccd-102">Opération MaybeChooseElement</span><span class="sxs-lookup"><span data-stu-id="deccd-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="deccd-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="deccd-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="deccd-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="deccd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="deccd-105">À partir d’un tableau de données et d’une distribution sur ses index, tente de choisir un élément au hasard.</span><span class="sxs-lookup"><span data-stu-id="deccd-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="deccd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="deccd-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="deccd-107">données : 't []</span><span class="sxs-lookup"><span data-stu-id="deccd-107">data : 'T[]</span></span>

<span data-ttu-id="deccd-108">Tableau à partir duquel un élément doit être choisi.</span><span class="sxs-lookup"><span data-stu-id="deccd-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="deccd-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="deccd-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="deccd-110">Distribution sur les index de `data` .</span><span class="sxs-lookup"><span data-stu-id="deccd-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="deccd-111">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="deccd-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="deccd-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="deccd-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="deccd-113">Peut</span><span class="sxs-lookup"><span data-stu-id="deccd-113">'T</span></span>

