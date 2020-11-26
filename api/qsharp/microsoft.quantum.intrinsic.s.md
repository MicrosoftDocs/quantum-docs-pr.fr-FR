---
uid: Microsoft.Quantum.Intrinsic.S
title: Opération S
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: c697408c4efe1963787b5aee8f0d3bb6b9e64dd5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198450"
---
# <a name="s-operation"></a>Opération S

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Applique la porte S à un qubit unique.

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Cette opération peut être simulée par la matrice \begin{align} S \mathrel{ : =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}.
\end{align}

## <a name="input"></a>Entrée

### <a name="qubit--qubit"></a>qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auquel la porte doit être appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

