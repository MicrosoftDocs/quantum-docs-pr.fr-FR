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
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="ab86a-102">Type défini par l’utilisateur PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="ab86a-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="ab86a-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ab86a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ab86a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab86a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab86a-105">Entiers non signés avec primauté des octets de poids faible (Little-endian) dans QFT.</span><span class="sxs-lookup"><span data-stu-id="ab86a-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="ab86a-106">Par exemple, si $ \ket{x} $ est l’encodage Little-endian de l’entier $x $ dans la base de calcul, alors $ \operatorname{QFTLE} \ket{x} $ est l’encodage de $x $ dans la base QFT.</span><span class="sxs-lookup"><span data-stu-id="ab86a-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="ab86a-107">Notes</span><span class="sxs-lookup"><span data-stu-id="ab86a-107">Remarks</span></span>

<span data-ttu-id="ab86a-108">Nous `PhaseLittleEndian` l’abrégeons `PhaseLE` dans la documentation.</span><span class="sxs-lookup"><span data-stu-id="ab86a-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab86a-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab86a-109">See Also</span></span>

- [<span data-ttu-id="ab86a-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="ab86a-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="ab86a-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="ab86a-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)