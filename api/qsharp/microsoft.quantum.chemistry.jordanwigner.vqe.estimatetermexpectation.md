---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Opération EstimateTermExpectation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703078"
---
# <a name="estimatetermexpectation-operation"></a>Opération EstimateTermExpectation

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Packages [](https://nuget.org/packages/)


Calcule l’énergie associée à un terme Jordan-Wigner Hamilton

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Description

Cette opération estime la valeur de prévision associée à chaque opérateur de mesure et la multiplie par le coefficient correspondant, à l’aide de l’échantillonnage.
Les résultats sont regroupés dans une variable contenant l’énergie du terme Jordan-Wigner.

## <a name="input"></a>Entrée

### <a name="inputstateunitary--qubit--unit-adj"></a>inputStateUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Unité utilisée pour la préparation de l’État.


### <a name="ops--pauli"></a>OPS : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Les opérateurs de mesure du terme Jordan-Wigner.


### <a name="coeffs--double"></a>coeffs : [double](xref:microsoft.quantum.lang-ref.double)[]

Coefficients du terme Jordan-Wigner.


### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits nécessaires pour simuler le système moléculaire.


### <a name="nsamples--int"></a>nSamples : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’échantillons à utiliser pour l’estimation du terme attendu.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

Énergie associée au terme de Jordan-Wigner.