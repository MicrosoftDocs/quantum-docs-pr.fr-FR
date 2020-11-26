---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Type défini par l’utilisateur LabeledSample
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196325"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="7cdd5-102">Type défini par l’utilisateur LabeledSample</span><span class="sxs-lookup"><span data-stu-id="7cdd5-102">LabeledSample user defined type</span></span>

<span data-ttu-id="7cdd5-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7cdd5-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7cdd5-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7cdd5-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7cdd5-105">Un exemple, étiqueté avec une classe à laquelle cet exemple appartient.</span><span class="sxs-lookup"><span data-stu-id="7cdd5-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="7cdd5-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="7cdd5-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="7cdd5-107">Fonctionnalités : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7cdd5-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7cdd5-108">Vecteur de fonctionnalités pour l’exemple donné.</span><span class="sxs-lookup"><span data-stu-id="7cdd5-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="7cdd5-109">Étiquette : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7cdd5-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7cdd5-110">Étiquette d’entier pour la classe à laquelle cet exemple appartient.</span><span class="sxs-lookup"><span data-stu-id="7cdd5-110">An integer label for the class to which this sample belongs.</span></span>