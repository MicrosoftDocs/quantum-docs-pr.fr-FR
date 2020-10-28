---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Opération EstimateFrequency
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703660"
---
# <a name="estimatefrequency-operation"></a>Opération EstimateFrequency

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Packages [](https://nuget.org/packages/)


À partir d’une préparation et d’une mesure, évalue la fréquence à laquelle cette mesure s’est déroulée (retourne `Zero` ) en effectuant un nombre donné d’essais.

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrée

### <a name="preparation--qubit--unit"></a>préparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Une opération $P $ qui prépare un État donné $ \rho $ sur son registre d’entrée.


### <a name="measurement--qubit--__invalidresult__"></a>mesure : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __non <Result> valide__ 

Une opération $M $ représentant la mesure de l’intérêt.


### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits sur lesquelles la préparation et la mesure se font.


### <a name="nmeasurements--int"></a>nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de fois où la mesure doit être exécutée afin d’estimer la fréquence d’intérêt.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

Estimation de $ \hat{p} $ de la fréquence avec laquelle $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ retourne `Zero` , obtenue à l’aide de l’estimateur binomiale non biaisé $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, où $n \_ {\uparrow} $ est le nombre de `Zero` résultats observés.

Cela est particulièrement important sur les ordinateurs cibles qui respectent les limitations physiques, de sorte que les probabilités ne peuvent pas être mesurées.