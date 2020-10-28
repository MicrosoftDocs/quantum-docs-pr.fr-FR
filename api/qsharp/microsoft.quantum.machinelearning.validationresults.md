---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: Type défini par l’utilisateur ValidationResults
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706814"
---
# <a name="validationresults-user-defined-type"></a>Type défini par l’utilisateur ValidationResults

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Le résultat de l’utilisation d’un classifieur sur un ensemble d’exemples est validé.

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>Éléments nommés

### <a name="nmisclassifications--int"></a>NMisclassifications : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de classifications incorrectes observées pendant la validation.
### <a name="nvalidationsamples--int"></a>NValidationSamples : [entier](xref:microsoft.quantum.lang-ref.int)

