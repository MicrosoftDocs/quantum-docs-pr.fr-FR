---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196308"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="d8635-102">NMisclassifications fonction)</span><span class="sxs-lookup"><span data-stu-id="d8635-102">NMisclassifications function</span></span>

<span data-ttu-id="d8635-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d8635-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d8635-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d8635-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d8635-105">Étant donné un ensemble d’étiquettes déduites et un ensemble d’étiquettes correctes, retourne le nombre d’index dont chaque ensemble d’étiquettes est différent.</span><span class="sxs-lookup"><span data-stu-id="d8635-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="d8635-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d8635-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="d8635-107">proposé : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d8635-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="d8635-108">réel : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d8635-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="d8635-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8635-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8635-110">Nombre d’index de ce `idx` type `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="d8635-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>