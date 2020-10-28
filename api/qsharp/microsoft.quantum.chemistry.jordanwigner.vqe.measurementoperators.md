---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703057"
---
# <a name="measurementoperators-function"></a>MeasurementOperators fonction)

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Packages [](https://nuget.org/packages/)


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