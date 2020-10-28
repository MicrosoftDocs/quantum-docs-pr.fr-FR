---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Type défini par l’utilisateur PhaseLittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706350"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="fde3d-102">Type défini par l’utilisateur PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="fde3d-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="fde3d-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fde3d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fde3d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fde3d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fde3d-105">Entiers non signés avec primauté des octets de poids faible (Little-endian) dans QFT.</span><span class="sxs-lookup"><span data-stu-id="fde3d-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="fde3d-106">Par exemple, si $ \ket{x} $ est l’encodage Little-endian de l’entier $x $ dans la base de calcul, alors $ \operatorname{QFTLE} \ket{x} $ est l’encodage de $x $ dans la base QFT.</span><span class="sxs-lookup"><span data-stu-id="fde3d-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="fde3d-107">Notes</span><span class="sxs-lookup"><span data-stu-id="fde3d-107">Remarks</span></span>

<span data-ttu-id="fde3d-108">Nous `PhaseLittleEndian` l’abrégeons `PhaseLE` dans la documentation.</span><span class="sxs-lookup"><span data-stu-id="fde3d-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="fde3d-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fde3d-109">See Also</span></span>

- [<span data-ttu-id="fde3d-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="fde3d-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="fde3d-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="fde3d-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)