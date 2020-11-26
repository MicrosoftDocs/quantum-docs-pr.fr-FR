---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: Opération EstimateOverlapBetweenStates
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 07693ccf4b8e7bbde189674d9e6b2bf7f92222f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204298"
---
# <a name="estimateoverlapbetweenstates-operation"></a>Opération EstimateOverlapBetweenStates

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir de deux opérations qui préparent les copies d’un État, évalue le chevauchement carré entre les États préparés par chaque opération.

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrée

### <a name="preparation1--qubit--unit--is-adj"></a>preparation1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

La première des deux opérations de préparation de l’État à comparer.


### <a name="preparation2--qubit--unit--is-adj"></a>preparation2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Deuxième des deux opérations de préparation de l’État à comparer.


### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits sur lesquels `commonPreparation` , `preparation1` et `preparation2` agissent.


### <a name="nmeasurements--int"></a>nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de mesures à utiliser pour estimer le chevauchement.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Notes

Cette opération utilise le test d’échange pour trouver $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $ où $U $ est la représentation unitaire de l’action de `preparation1` , et où $V $ correspond à `preparation2` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. caractérisation. EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. Quantum. caractérisation. EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)