---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: Type défini par l’utilisateur BigEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707435"
---
# <a name="bigendian-user-defined-type"></a>Type défini par l’utilisateur BigEndian

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Inscrivez-vous pour encoder un entier non signé dans l’ordre Big-endian. Le qubit avec l’index `0` encode le bit le plus élevé d’un entier non signé.

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>Notes

Nous `BigEndian` l’abrégeons `BE` dans la documentation.