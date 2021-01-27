---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Opération de MAJ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846549"
---
# <a name="maj-operation"></a>Opération de MAJ

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Cela applique la majorité en place à 3 qubits.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Si nous désignerons l’état du qubit cible en tant que $ \ket{z} $, et les États d’entrée du qubits d’entrée comme $ \ket{x} $ et $ \ket{y} $, cette opération effectue la transformation suivante : $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Entrée

### <a name="input0--qubit"></a>input0 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Premier qubit d’entrée.


### <a name="input1--qubit"></a>ENTRÉE1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Deuxième qubit d’entrée.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit sur lequel la fonction majoritaire sera appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

