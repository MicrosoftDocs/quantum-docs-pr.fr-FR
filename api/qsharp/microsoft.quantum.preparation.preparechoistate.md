---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Opération PrepareChoiState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: ced71c4278f42f577760acd54ae53e7f5e6dae4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210571"
---
# <a name="preparechoistate-operation"></a>Opération PrepareChoiState

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prépare l’État Choi – Jamiołkowski pour une opération donnée sur des registres de référence et cibles donnés.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="op--qubit--unit"></a>OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

L’opération $ \Lambda $ dont l’État Choi – Jamiołkowski $J (\Lambda)/2 ^ N $ doit être préparée, où $N $ est le nombre de qubits sur lequel `op` agit.


### <a name="reference--qubit"></a>Référence : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre de qubits à partir de l’État $ \ket{00\cdots 0} $ à utiliser comme référence pour l’action de `op` .


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre de qubits initialement dans l’État $ \ket{00\cdots 0} $ sur lequel `op` doit être appliqué.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’État Choi – Jamiłkowski $J (\Lambda) $ d’un processus Quantum est défini en tant que $ $ \begin{align} J (\Lambda) \mathrel{ : =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ où $ | X\rangle \! \rangle $ est la *vectorisation* d’une matrice $X $ dans la Convention d’empilement de colonnes. L’apprentissage d’une description classique de cet État fournit des informations complètes sur l’effet de $ \Lambda $ agissant sur des États d’entrée arbitraires et constitue la base de la *tomographie de processus quantique*.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PREPARATION. PrepareChoiStateA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft. Quantum. PREPARATION. PrepareChoiStateC](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft. Quantum. PREPARATION. PrepareChoiStateCA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)