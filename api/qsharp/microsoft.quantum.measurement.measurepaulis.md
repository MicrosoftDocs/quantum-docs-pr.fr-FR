---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Opération MeasurePaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853767"
---
# <a name="measurepaulis-operation"></a>Opération MeasurePaulis

Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau d’opérateurs Pauli à plusieurs qubit, les mesures de chacune à l’aide d’un gadget de mesure spécifié, puis retourne le tableau de résultats.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Entrée

### <a name="paulis--pauli"></a>Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tableau d’opérateurs Pauli à plusieurs qubit à mesurer.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Inscrivez-vous pour mesurer les opérateurs donnés.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valide__ 

Opération qui effectue la mesure d’un opérateur multi-qubit donné.



## <a name="output--__invalidresult__"></a>Sortie : [] __non valide <Result>__

Tableau de résultats obtenus à partir de la mesure de chaque élément de `paulis` on `target` .