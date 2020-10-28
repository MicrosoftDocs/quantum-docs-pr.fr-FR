---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Opération MeasureStabilizerGenerators
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702451"
---
# <a name="measurestabilizergenerators-operation"></a>Opération MeasureStabilizerGenerators

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


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


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valide__ 

Opération qui spécifie comment mesurer un opérateur multiqubit Pauli.



## <a name="output--syndrome"></a>Sortie : [syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Résultat des mesures.

## <a name="remarks"></a>Notes

Cela ne vérifie pas si l’ensemble donné de générateurs se transporte.
Dans le cas contraire, le résultat des mesures peut être arbitraire.