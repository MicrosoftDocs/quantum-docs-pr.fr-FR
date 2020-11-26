---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Opération PrepareIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210435"
---
# <a name="prepareidentity-operation"></a>Opération PrepareIdentity

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pour un registre donné, prépare ce registre dans l’état le plus maximal mélangé.

Le Registre est préparé dans l’État $ \boldone/2 ^ N $ en appliquant le canal de dépolarisation complet à chaque qubit, où $N $ est la longueur du Registre.

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="register--qubit"></a>Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre dont l’État doit être dépolarisé de la manière décrite ci-dessus.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PREPARATION. PrepareSingleQubitIdentity](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)