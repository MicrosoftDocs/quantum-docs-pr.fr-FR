---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708345"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Retourne le nombre de qubits nécessaires pour encoder un vecteur de fonctionnalité particulier.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Entrée

### <a name="sample--double"></a>exemple : [double](xref:microsoft.quantum.lang-ref.double)[]

Exemple de vecteur de fonctionnalité à encoder dans un registre qubit.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Taille requise pour encoder `sample` dans un registre qubit, exprimée sous la forme d’un nombre de qubits.