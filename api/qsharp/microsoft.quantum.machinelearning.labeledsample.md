---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Type défini par l’utilisateur LabeledSample
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702052"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="89283-102">Type défini par l’utilisateur LabeledSample</span><span class="sxs-lookup"><span data-stu-id="89283-102">LabeledSample user defined type</span></span>

<span data-ttu-id="89283-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="89283-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="89283-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89283-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89283-105">Un exemple, étiqueté avec une classe à laquelle cet exemple appartient.</span><span class="sxs-lookup"><span data-stu-id="89283-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="89283-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="89283-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="89283-107">Fonctionnalités : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="89283-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="89283-108">Vecteur de fonctionnalités pour l’exemple donné.</span><span class="sxs-lookup"><span data-stu-id="89283-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="89283-109">Étiquette : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89283-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89283-110">Étiquette d’entier pour la classe à laquelle cet exemple appartient.</span><span class="sxs-lookup"><span data-stu-id="89283-110">An integer label for the class to which this sample belongs.</span></span>