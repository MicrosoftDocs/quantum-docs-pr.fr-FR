---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: Type défini par l’utilisateur ValidationResults
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846087"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="b0196-102">Type défini par l’utilisateur ValidationResults</span><span class="sxs-lookup"><span data-stu-id="b0196-102">ValidationResults user defined type</span></span>

<span data-ttu-id="b0196-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b0196-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b0196-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b0196-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b0196-105">Le résultat de l’utilisation d’un classifieur sur un ensemble d’exemples est validé.</span><span class="sxs-lookup"><span data-stu-id="b0196-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="b0196-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="b0196-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="b0196-107">NMisclassifications : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0196-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0196-108">Nombre de classifications incorrectes observées pendant la validation.</span><span class="sxs-lookup"><span data-stu-id="b0196-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="b0196-109">NValidationSamples : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0196-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

