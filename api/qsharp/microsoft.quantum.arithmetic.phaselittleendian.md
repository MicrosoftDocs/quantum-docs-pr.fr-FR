---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Type défini par l’utilisateur PhaseLittleEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222420"
---
# <a name="phaselittleendian-user-defined-type"></a>Type défini par l’utilisateur PhaseLittleEndian

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Entiers non signés avec primauté des octets de poids faible (Little-endian) dans QFT.

Par exemple, si $ \ket{x} $ est l’encodage Little-endian de l’entier $x $ dans la base de calcul, alors $ \operatorname{QFTLE} \ket{x} $ est l’encodage de $x $ dans la base QFT.

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Notes

Nous `PhaseLittleEndian` l’abrégeons `PhaseLE` dans la documentation.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Microsoft. Quantum. Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)