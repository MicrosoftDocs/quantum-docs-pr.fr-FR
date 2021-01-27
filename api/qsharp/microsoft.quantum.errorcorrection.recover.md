---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Opération de récupération
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: 3e2ce404ae3a6b4097897b859388fea3f915232c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825518"
---
# <a name="recover-operation"></a>Opération de récupération

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Effectue un seul arrondi de correction d’erreur par un code de Quantum décrit par un `QECC` type.

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Entrée

### <a name="code--qecc"></a>Code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Un code de correction des erreurs de Quantum empaqueté en tant que `QECC` type décrit l’encodage et le décodage des données Quantum, ainsi que la mesure des syndromes d’erreur.


### <a name="fn--recoveryfn"></a>FN : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`Qui mappe chaque syndrome d’erreur aux `Pauli[]` opérations qui corrigent l’erreur détectée.


### <a name="logicalregister--logicalregister"></a>logicalRegister : [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Tableau de qubits où le code stabilisant est défini.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)