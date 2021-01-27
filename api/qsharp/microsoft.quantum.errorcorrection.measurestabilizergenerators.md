---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Opération MeasureStabilizerGenerators
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825751"
---
# <a name="measurestabilizergenerators-operation"></a>Opération MeasureStabilizerGenerators

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mesure le jeu de générateurs donné d’un groupe stabilisant.

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>Entrée

### <a name="stabilizergroup--pauli"></a>stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tableau d’opérateurs Pauli multiqubit.
Par exemple, `stabilizerGroup[0]` est une liste de matrices Pauli à qubit unique, dont le produit tenseur est un générateur stabilisant.


### <a name="logicalregister--logicalregister"></a>logicalRegister : [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Tableau de qubits où le code stabilisant est défini.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valide__ 

Opération qui spécifie comment mesurer un opérateur multiqubit Pauli.



## <a name="output--syndrome"></a>Sortie : [syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Résultat des mesures.

## <a name="remarks"></a>Notes

Cela ne vérifie pas si l’ensemble donné de générateurs se transporte.
Dans le cas contraire, le résultat des mesures peut être arbitraire.