---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: Type défini par l’utilisateur ValidationResults
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 42bfab7fd1f9372d9394f2eaf2d698b39b4307e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211489"
---
# <a name="validationresults-user-defined-type"></a>Type défini par l’utilisateur ValidationResults

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Le résultat de l’utilisation d’un classifieur sur un ensemble d’exemples est validé.

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>Éléments nommés

### <a name="nmisclassifications--int"></a>NMisclassifications : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de classifications incorrectes observées pendant la validation.
### <a name="nvalidationsamples--int"></a>NValidationSamples : [entier](xref:microsoft.quantum.lang-ref.int)

