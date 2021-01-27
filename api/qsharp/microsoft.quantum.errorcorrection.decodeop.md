---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: Type défini par l’utilisateur DecodeOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 2b3d4558f6528c2e0f597398d12fc9331ab381b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827370"
---
# <a name="decodeop-user-defined-type"></a>Type défini par l’utilisateur DecodeOp

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une opération qui décode un registre encodé en registre physique et le qubits Scratch utilisé pour enregistrer un syndrome.

L’argument d’un DecodeOp est le même que le retour d’un EncodeOp, et vice versa.

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

