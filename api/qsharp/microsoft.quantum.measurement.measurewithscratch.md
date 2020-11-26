---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Opération MeasureWithScratch
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227061"
---
# <a name="measurewithscratch-operation"></a>Opération MeasureWithScratch

Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mesure l’opérateur Pauli donné à l’aide d’un qubit de travail explicite pour effectuer la mesure.

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>Entrée

### <a name="pauli--pauli"></a>Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Opérateur qubit Pauli spécifié sous la forme d’un tableau d’opérateurs Pauli qubit uniques.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre qubit à mesurer.



## <a name="output--__invalidresult__"></a>Sortie : __non <Result> valide__

Résultat de la mesure de l’opérateur Pauli donné sur le `target` Registre.