---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: Opération ApplyUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859164"
---
# <a name="applyunitary-operation"></a>Opération ApplyUnitary

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique la porte définie par la matrice unitaire 2 ^ n x 2 ^ n.

Échoue si la matrice n’est pas une unité ou a une taille incorrecte.

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="unitary--complex"></a>Unity : [complexe](xref:Microsoft.Quantum.Math.Complex)[] []

2 ^ n x 2 ^ n matrice d’unités décrivant l’opération.
Si la matrice n’est pas une unité ou une taille appropriée, lève une exception.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubits auquel appliquer l’opération-Registre de longueur n.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

