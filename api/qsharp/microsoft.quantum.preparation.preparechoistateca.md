---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: Opération PrepareChoiStateCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: b9d2cdaea1ebc957719d92bf12901c54a55a56aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701242"
---
# <a name="preparechoistateca-operation"></a>Opération PrepareChoiStateCA

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Packages [](https://nuget.org/packages/)


Prépare l’État Choi – Jamiłkowski pour une opération donnée avec des variantes contrôlées et voisines sur des registres de référence et cibles donnés.

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="op--qubit--unit-adj--ctl"></a>OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="reference--qubit"></a>Référence : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PREPARATION. PrepareChoiState](xref:Microsoft.Quantum.Preparation.PrepareChoiState)