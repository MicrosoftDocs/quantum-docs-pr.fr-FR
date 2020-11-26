---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 2e39318cfaf3321c33b08f742bb25a9276b7e660
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196597"
---
# <a name="approximateinputencoder-function"></a>ApproximateInputEncoder fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


À partir d’un ensemble de coefficients et d’une tolérance, retourne une opération de préparation de l’État qui prépare chaque coefficient comme amplitude correspondante d’un état de base de calcul, jusqu’à la tolérance donnée.

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Entrée

### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance approximative à utiliser pour encoder les coefficients donnés dans un état d’entrée.


### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Coefficients à encoder dans un état d’entrée.



## <a name="output--stategenerator"></a>Sortie : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Opération de préparation de l’État qui prépare les coefficients donnés comme un état d’entrée sur un registre donné.