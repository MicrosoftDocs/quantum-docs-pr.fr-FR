---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Opération MaybeChooseElement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707865"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="790eb-102">Opération MaybeChooseElement</span><span class="sxs-lookup"><span data-stu-id="790eb-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="790eb-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="790eb-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="790eb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="790eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="790eb-105">À partir d’un tableau de données et d’une distribution sur ses index, tente de choisir un élément au hasard.</span><span class="sxs-lookup"><span data-stu-id="790eb-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="790eb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="790eb-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="790eb-107">données : 't []</span><span class="sxs-lookup"><span data-stu-id="790eb-107">data : 'T[]</span></span>

<span data-ttu-id="790eb-108">Tableau à partir duquel un élément doit être choisi.</span><span class="sxs-lookup"><span data-stu-id="790eb-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="790eb-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="790eb-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="790eb-110">Distribution sur les index de `data` .</span><span class="sxs-lookup"><span data-stu-id="790eb-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="790eb-111">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="790eb-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="790eb-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="790eb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="790eb-113">Peut</span><span class="sxs-lookup"><span data-stu-id="790eb-113">'T</span></span>

