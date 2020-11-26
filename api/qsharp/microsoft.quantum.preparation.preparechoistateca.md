---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: Opération PrepareChoiStateCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: abe75865149c985426a5eaf69cf41433829e1916
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210486"
---
# <a name="preparechoistateca-operation"></a>Opération PrepareChoiStateCA

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prépare l’État Choi – Jamiołkowski pour une opération donnée avec des variantes contrôlées et voisines sur des registres de référence et cibles donnés.

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="op--qubit--unit--is-adj--ctl"></a>OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL




### <a name="reference--qubit"></a>Référence : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PREPARATION. PrepareChoiState](xref:Microsoft.Quantum.Preparation.PrepareChoiState)