---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Fonction incorrecte de classification
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211676"
---
# <a name="misclassifications-function"></a><span data-ttu-id="c5a44-102">Fonction incorrecte de classification</span><span class="sxs-lookup"><span data-stu-id="c5a44-102">Misclassifications function</span></span>

<span data-ttu-id="c5a44-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c5a44-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c5a44-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c5a44-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c5a44-105">Étant donné un ensemble d’étiquettes déduites et un ensemble d’étiquettes correctes, retourne des index pour chaque ensemble d’étiquettes.</span><span class="sxs-lookup"><span data-stu-id="c5a44-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c5a44-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c5a44-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="c5a44-107">inferredLabels : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c5a44-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c5a44-108">Étiquettes déduites pour un ensemble d’apprentissage ou un jeu de validation donné.</span><span class="sxs-lookup"><span data-stu-id="c5a44-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="c5a44-109">actualLabels : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c5a44-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c5a44-110">Étiquettes vraies pour un ensemble d’apprentissage ou un jeu de validation donné.</span><span class="sxs-lookup"><span data-stu-id="c5a44-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="c5a44-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c5a44-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c5a44-112">Tableau d’index de ce `idx` type `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="c5a44-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>