---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: Opération RecoverCSS
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: 48d3cd3d5f6aea265fac2f50b913ab855a31accf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702424"
---
# <a name="recovercss-operation"></a>Opération RecoverCSS

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


Effectue un seul arrondi de correction d’erreur par un code de Quantum décrit par un `CSS` type.

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Entrée

### <a name="code--css"></a>Code : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Un code de correction des erreurs CSS de Quantum sous la forme d’un `CSS` type décrit l’encodage et le décodage des données Quantum, ainsi que la mesure des syndromes des erreurs.


### <a name="fnx--recoveryfn"></a>fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`Qui mappe chaque $X $ Error syndrome aux `Pauli[]` opérations qui corrigent l’erreur détectée.


### <a name="fnz--recoveryfn"></a>fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`Qui mappe chaque $Z $ Error syndrome aux `Pauli[]` opérations qui corrigent l’erreur détectée.


### <a name="logicalregister--logicalregister"></a>logicalRegister : [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Tableau de qubits où le code stabilisant est défini.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)