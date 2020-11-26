---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: Opération ApplySequentialClassifier
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: fe1ca5717f18cc0816b96ddd29ce89c568571791
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212016"
---
# <a name="applysequentialclassifier-operation"></a>Opération ApplySequentialClassifier

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Compte tenu de la structure et du paramétrage d’un classifieur séquentiel, applique le classifieur à un registre de qubits.

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="model--sequentialmodel"></a>modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)




### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre cible auquel le classifieur doit être appliqué.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

