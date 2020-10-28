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
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="64bb9-102">Type défini par l’utilisateur BigEndian</span><span class="sxs-lookup"><span data-stu-id="64bb9-102">BigEndian user defined type</span></span>

<span data-ttu-id="64bb9-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="64bb9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="64bb9-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64bb9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64bb9-105">Inscrivez-vous pour encoder un entier non signé dans l’ordre Big-endian.</span><span class="sxs-lookup"><span data-stu-id="64bb9-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="64bb9-106">Le qubit avec l’index `0` encode le bit le plus élevé d’un entier non signé.</span><span class="sxs-lookup"><span data-stu-id="64bb9-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="64bb9-107">Notes</span><span class="sxs-lookup"><span data-stu-id="64bb9-107">Remarks</span></span>

<span data-ttu-id="64bb9-108">Nous `BigEndian` l’abrégeons `BE` dans la documentation.</span><span class="sxs-lookup"><span data-stu-id="64bb9-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>