---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: a5ea9a776f522e927f2f4545bd417d35bda83994
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214345"
---
# <a name="measurementoperators-function"></a>MeasurementOperators fonction)

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Calcule tous les opérateurs de mesure requis pour calculer l’attente d’un terme Jordan-Wigner.

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits nécessaires pour simuler le système moléculaire.


### <a name="indices--int"></a>index : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau contenant les index du qubit auquel chaque opérateur Pauli est appliqué.


### <a name="termtype--int"></a>termType : [entier](xref:microsoft.quantum.lang-ref.int)

Type du terme Jordan-Wigner.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tableau d’opérateurs de mesure (chacun étant un tableau de Pauli).