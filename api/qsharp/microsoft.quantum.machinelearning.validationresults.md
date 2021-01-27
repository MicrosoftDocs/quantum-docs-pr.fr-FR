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

