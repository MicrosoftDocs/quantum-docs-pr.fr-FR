---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: Type défini par l’utilisateur BigEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223661"
---
# <a name="bigendian-user-defined-type"></a>Type défini par l’utilisateur BigEndian

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Inscrivez-vous pour encoder un entier non signé dans l’ordre Big-endian. Le qubit avec l’index `0` encode le bit le plus élevé d’un entier non signé.

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>Notes

Nous `BigEndian` l’abrégeons `BE` dans la documentation.