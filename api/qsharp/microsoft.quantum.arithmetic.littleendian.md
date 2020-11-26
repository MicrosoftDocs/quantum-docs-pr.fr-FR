---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: Type défini par l’utilisateur LittleEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222777"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="c976e-102">Type défini par l’utilisateur LittleEndian</span><span class="sxs-lookup"><span data-stu-id="c976e-102">LittleEndian user defined type</span></span>

<span data-ttu-id="c976e-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c976e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c976e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c976e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c976e-105">Inscrivez-vous pour encoder un entier non signé dans l’ordre de primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="c976e-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="c976e-106">Le qubit avec l’index `0` encode le bit le plus bas d’un entier non signé.</span><span class="sxs-lookup"><span data-stu-id="c976e-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="c976e-107">Notes</span><span class="sxs-lookup"><span data-stu-id="c976e-107">Remarks</span></span>

<span data-ttu-id="c976e-108">Nous `LittleEndian` l’abrégeons `LE` dans la documentation.</span><span class="sxs-lookup"><span data-stu-id="c976e-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>