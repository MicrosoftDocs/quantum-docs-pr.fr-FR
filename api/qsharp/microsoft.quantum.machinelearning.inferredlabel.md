---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708015"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="54675-102">InferredLabel fonction)</span><span class="sxs-lookup"><span data-stu-id="54675-102">InferredLabel function</span></span>

<span data-ttu-id="54675-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="54675-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="54675-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54675-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54675-105">Étant donné un de probabilité de classification et un biais, retourne l’étiquette déduite de cette probabilité.</span><span class="sxs-lookup"><span data-stu-id="54675-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="54675-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="54675-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="54675-107">biais : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="54675-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="54675-108">Le décalage entre deux classes, généralement le résultat de l’apprentissage d’un classifieur.</span><span class="sxs-lookup"><span data-stu-id="54675-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="54675-109">probabilité : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="54675-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="54675-110">Probabilités de classification pour un échantillon donné, en général résultant de l’estimation de sa fréquence de classification.</span><span class="sxs-lookup"><span data-stu-id="54675-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="54675-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="54675-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="54675-112">Étiquette déduite de la probabilité de classification donnée.</span><span class="sxs-lookup"><span data-stu-id="54675-112">The label inferred from the given classification probability.</span></span>