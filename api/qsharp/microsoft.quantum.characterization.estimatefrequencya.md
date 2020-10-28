---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Opération EstimateFrequencyA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 88f0a237975c158bffcc015f79d2134b210ce83b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703651"
---
# <a name="estimatefrequencya-operation"></a>Opération EstimateFrequencyA

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Packages [](https://nuget.org/packages/)


Étant donné une préparation qui est adjointable et mesure, évalue la fréquence à laquelle cette mesure s’est déroulée (retourne `Zero` ) en effectuant un nombre donné d’essais.

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrée

### <a name="preparation--qubit--unit-adj"></a>préparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Une opération adjointable $P $ qui prépare un État donné $ \rho $ dans son registre d’entrée.


### <a name="measurement--qubit--__invalidresult__"></a>mesure : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __non <Result> valide__ 

Une opération $M $ représentant la mesure de l’intérêt.


### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits sur lesquelles la préparation et la mesure se font.


### <a name="nmeasurements--int"></a>nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de fois où la mesure doit être exécutée afin d’estimer la fréquence d’intérêt.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

Estimation de $ \hat{p} $ de la fréquence avec laquelle $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ retourne `Zero` , obtenue à l’aide de l’estimateur binomiale non biaisé $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, où $n \_ {\uparrow} $ est le nombre de `Zero` résultats observés.

## <a name="remarks"></a>Notes

Pour les opérations adjointable, certaines hypothèses peuvent être apportées telles que l’appel de l’opération prépare le qubits à exactement le même État, ce qui permet aux ordinateurs cibles d’effectuer des optimisations de performances.