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
# <a name="labeledsample-user-defined-type"></a>Type défini par l’utilisateur LabeledSample

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Un exemple, étiqueté avec une classe à laquelle cet exemple appartient.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Éléments nommés

### <a name="features--double"></a>Fonctionnalités : [double](xref:microsoft.quantum.lang-ref.double)[]

Vecteur de fonctionnalités pour l’exemple donné.
### <a name="label--int"></a>Étiquette : [entier](xref:microsoft.quantum.lang-ref.int)

Étiquette d’entier pour la classe à laquelle cet exemple appartient.