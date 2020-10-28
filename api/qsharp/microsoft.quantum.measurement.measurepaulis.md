---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Opération MeasurePaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706758"
---
# <a name="measurepaulis-operation"></a>Opération MeasurePaulis

Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Packages [](https://nuget.org/packages/)


À partir d’un tableau d’opérateurs Pauli à plusieurs qubit, les mesures de chacune à l’aide d’un gadget de mesure spécifié, puis retourne le tableau de résultats.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Entrée

### <a name="paulis--pauli"></a>Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tableau d’opérateurs Pauli à plusieurs qubit à mesurer.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Inscrivez-vous pour mesurer les opérateurs donnés.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valide__ 

Opération qui effectue la mesure d’un opérateur multi-qubit donné.



## <a name="output--__invalidresult__"></a>Sortie : [] __non valide <Result>__

Tableau de résultats obtenus à partir de la mesure de chaque élément de `paulis` on `target` .