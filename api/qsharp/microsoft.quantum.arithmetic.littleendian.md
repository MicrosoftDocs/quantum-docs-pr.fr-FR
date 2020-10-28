---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: Type défini par l’utilisateur LittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707227"
---
# <a name="littleendian-user-defined-type"></a>Type défini par l’utilisateur LittleEndian

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Inscrivez-vous pour encoder un entier non signé dans l’ordre de primauté des octets de poids faible. Le qubit avec l’index `0` encode le bit le plus bas d’un entier non signé.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Notes

Nous `LittleEndian` l’abrégeons `LE` dans la documentation.