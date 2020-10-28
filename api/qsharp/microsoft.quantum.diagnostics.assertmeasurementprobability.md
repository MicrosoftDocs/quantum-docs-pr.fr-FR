---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Opération AssertMeasurementProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702757"
---
# <a name="assertmeasurementprobability-operation"></a>Opération AssertMeasurementProbability

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Les assertions qui mesurent le qubits donné dans la base Pauli donnée auront le résultat donné avec la probabilité donnée, dans une certaine tolérance.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a>Entrée

### <a name="bases--pauli"></a>bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Effet de mesure permettant de déclarer la probabilité de, exprimée sous la forme d’un opérateur qubit Pauli.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre sur lequel effectuer l’assertion.


### <a name="result--__invalidresult__"></a>résultat : __non <Result> valide__

Résultat attendu de `Measure(bases, qubits)` .


### <a name="prob--double"></a>sonde : [double](xref:microsoft.quantum.lang-ref.double)

Probabilité avec laquelle le résultat donné est attendu.


### <a name="msg--string"></a>MSG : [chaîne](xref:microsoft.quantum.lang-ref.string)

Message à signaler si l’assertion échoue.


### <a name="tol--double"></a>tol : [double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Notez que les versions adjacentes et contrôlées de cette opération ne vérifient pas la condition.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Diagnostics. AssertMeasurement](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)