---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196410"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Retourne le nombre de qubits nécessaires pour encoder un vecteur de fonctionnalité particulier.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Entrée

### <a name="sample--double"></a>exemple : [double](xref:microsoft.quantum.lang-ref.double)[]

Exemple de vecteur de fonctionnalité à encoder dans un registre qubit.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Taille requise pour encoder `sample` dans un registre qubit, exprimée sous la forme d’un nombre de qubits.