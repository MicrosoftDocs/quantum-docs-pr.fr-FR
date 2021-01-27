---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: Type défini par l’utilisateur LittleEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846562"
---
# <a name="littleendian-user-defined-type"></a>Type défini par l’utilisateur LittleEndian

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Inscrivez-vous pour encoder un entier non signé dans l’ordre de primauté des octets de poids faible. Le qubit avec l’index `0` encode le bit le plus bas d’un entier non signé.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Notes

Nous `LittleEndian` l’abrégeons `LE` dans la documentation.