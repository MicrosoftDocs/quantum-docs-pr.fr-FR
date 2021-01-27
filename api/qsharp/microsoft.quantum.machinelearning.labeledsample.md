---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Type défini par l’utilisateur LabeledSample
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846976"
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