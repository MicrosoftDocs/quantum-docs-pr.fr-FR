---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: e910edb9bf432e6acb5c349ee6b9d65797aaaba7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211659"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="a4605-102">NQubitsRequired fonction)</span><span class="sxs-lookup"><span data-stu-id="a4605-102">NQubitsRequired function</span></span>

<span data-ttu-id="a4605-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a4605-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a4605-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a4605-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a4605-105">Retourne le nombre d’qubits requis pour appliquer un classifieur séquentiel donné.</span><span class="sxs-lookup"><span data-stu-id="a4605-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="a4605-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a4605-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="a4605-107">modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="a4605-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="a4605-108">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a4605-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a4605-109">Taille minimale d’un registre sur lequel le classifieur séquentiel peut être appliqué.</span><span class="sxs-lookup"><span data-stu-id="a4605-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>