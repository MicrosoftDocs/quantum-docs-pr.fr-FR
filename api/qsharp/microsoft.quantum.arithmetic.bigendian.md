---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: Type défini par l’utilisateur BigEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843395"
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