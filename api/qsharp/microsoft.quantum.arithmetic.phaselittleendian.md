---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Type défini par l’utilisateur PhaseLittleEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843000"
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