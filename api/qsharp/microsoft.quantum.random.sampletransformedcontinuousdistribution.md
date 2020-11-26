---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: Opération SampleTransformedContinuousDistribution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: f9f2b3cbbb4423f267758976cd066abbfec93a77
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192687"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a>Opération SampleTransformedContinuousDistribution

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Opération interne uniquement pour l’échantillonnage à partir de distributions transformées.
Doit être utilisé uniquement par le biais d’une application partielle.

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a>Entrée

### <a name="transform--double---double"></a>transformation : [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)




### <a name="distribution--continuousdistribution"></a>distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)





## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

