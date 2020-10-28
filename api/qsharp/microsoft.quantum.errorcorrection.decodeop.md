---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: Type défini par l’utilisateur DecodeOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 0733ec016e50a320b162b111c7d87c32140fdacb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702514"
---
# <a name="decodeop-user-defined-type"></a>Type défini par l’utilisateur DecodeOp

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


Représente une opération qui décode un registre encodé en registre physique et le qubits Scratch utilisé pour enregistrer un syndrome.

L’argument d’un DecodeOp est le même que le retour d’un EncodeOp, et vice versa.

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

