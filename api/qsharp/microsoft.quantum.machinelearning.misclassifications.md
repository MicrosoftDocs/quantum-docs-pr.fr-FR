---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Fonction incorrecte de classification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853924"
---
# <a name="misclassifications-function"></a><span data-ttu-id="1a7e1-102">Fonction incorrecte de classification</span><span class="sxs-lookup"><span data-stu-id="1a7e1-102">Misclassifications function</span></span>

<span data-ttu-id="1a7e1-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1a7e1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1a7e1-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1a7e1-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="1a7e1-105">Étant donné un ensemble d’étiquettes déduites et un ensemble d’étiquettes correctes, retourne des index pour chaque ensemble d’étiquettes.</span><span class="sxs-lookup"><span data-stu-id="1a7e1-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="1a7e1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1a7e1-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="1a7e1-107">inferredLabels : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1a7e1-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1a7e1-108">Étiquettes déduites pour un ensemble d’apprentissage ou un jeu de validation donné.</span><span class="sxs-lookup"><span data-stu-id="1a7e1-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="1a7e1-109">actualLabels : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1a7e1-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1a7e1-110">Étiquettes vraies pour un ensemble d’apprentissage ou un jeu de validation donné.</span><span class="sxs-lookup"><span data-stu-id="1a7e1-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="1a7e1-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1a7e1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1a7e1-112">Tableau d’index de ce `idx` type `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="1a7e1-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>

## <a name="example"></a><span data-ttu-id="1a7e1-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="1a7e1-113">Example</span></span>

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```