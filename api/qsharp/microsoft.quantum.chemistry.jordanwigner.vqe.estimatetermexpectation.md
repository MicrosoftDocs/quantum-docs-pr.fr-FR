---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Opération EstimateTermExpectation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835667"
---
# <a name="estimatetermexpectation-operation"></a>Opération EstimateTermExpectation

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Calcule l’énergie associée à un terme Jordan-Wigner Hamilton

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Description

Cette opération estime la valeur de prévision associée à chaque opérateur de mesure et la multiplie par le coefficient correspondant, à l’aide de l’échantillonnage.
Les résultats sont regroupés dans une variable contenant l’énergie du terme Jordan-Wigner.

## <a name="input"></a>Entrée

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

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