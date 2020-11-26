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
# <a name="labeledsample-user-defined-type"></a>Type défini par l’utilisateur LabeledSample

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Un exemple, étiqueté avec une classe à laquelle cet exemple appartient.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Éléments nommés

### <a name="features--double"></a>Fonctionnalités : [double](xref:microsoft.quantum.lang-ref.double)[]

Vecteur de fonctionnalités pour l’exemple donné.
### <a name="label--int"></a>Étiquette : [entier](xref:microsoft.quantum.lang-ref.int)

Étiquette d’entier pour la classe à laquelle cet exemple appartient.