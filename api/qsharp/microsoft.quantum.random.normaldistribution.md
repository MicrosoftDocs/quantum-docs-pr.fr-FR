---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814181"
---
# <a name="normaldistribution-function"></a>NormalDistribution fonction)

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Retourne une distribution normale avec une moyenne et une variance données.

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Entrée

### <a name="mean--double"></a>moyenne : [double](xref:microsoft.quantum.lang-ref.double)




### <a name="variance--double"></a>variance : [double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--continuousdistribution"></a>Sortie : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>Exemple

L’exemple suivant dessine 10 échantillons de la distribution normale avec la moyenne 2 et l’écart type 0,1 :

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Random. StandardNormalDistribution](xref:Microsoft.Quantum.Random.StandardNormalDistribution)