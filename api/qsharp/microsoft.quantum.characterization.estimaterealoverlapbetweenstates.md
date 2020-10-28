---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: Opération EstimateRealOverlapBetweenStates
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703612"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a>Opération EstimateRealOverlapBetweenStates

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Packages [](https://nuget.org/packages/)


À partir de deux opérations qui préparent les copies d’un État, évalue la partie réelle du chevauchement entre les États préparés par chaque opération.

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrée

### <a name="commonpreparation--qubit--unit-adj"></a>commonPreparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération qui prépare un état d’entrée fixe.


### <a name="preparation1--qubit--unit-adj--ctl"></a>preparation1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL

La première des deux opérations de préparation de l’État à comparer.


### <a name="preparation2--qubit--unit-adj--ctl"></a>preparation2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL

Deuxième des deux opérations de préparation de l’État à comparer.


### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits sur lesquels `commonPreparation` , `preparation1` et `preparation2` agissent.


### <a name="nmeasurements--int"></a>nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de mesures à utiliser pour estimer le chevauchement.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Notes

Cette opération utilise le test Hadarmard pour rechercher la partie réelle de $ $ \begin{align} \braket{\Psi | V ^ {\dagger} U | \Psi} \end{align} $ $ où $ \ket{\Psi} $ est l’état préparé par `commonPreparation` , $U $ est la représentation unitaire de l’action de `preparation1` , et où $V $ correspond à `preparation2` .

## <a name="references"></a>Références

- Aharonov *et al.* [quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. caractérisation. EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [Microsoft. Quantum. caractérisation. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)