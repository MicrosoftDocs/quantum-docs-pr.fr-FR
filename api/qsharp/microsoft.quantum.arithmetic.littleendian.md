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
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="aa454-102">Type défini par l’utilisateur LittleEndian</span><span class="sxs-lookup"><span data-stu-id="aa454-102">LittleEndian user defined type</span></span>

<span data-ttu-id="aa454-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aa454-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aa454-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa454-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa454-105">Inscrivez-vous pour encoder un entier non signé dans l’ordre de primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="aa454-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="aa454-106">Le qubit avec l’index `0` encode le bit le plus bas d’un entier non signé.</span><span class="sxs-lookup"><span data-stu-id="aa454-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="aa454-107">Notes</span><span class="sxs-lookup"><span data-stu-id="aa454-107">Remarks</span></span>

<span data-ttu-id="aa454-108">Nous `LittleEndian` l’abrégeons `LE` dans la documentation.</span><span class="sxs-lookup"><span data-stu-id="aa454-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>