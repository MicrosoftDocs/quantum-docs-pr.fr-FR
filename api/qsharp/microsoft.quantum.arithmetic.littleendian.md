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
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="5fa4f-102">Type défini par l’utilisateur LittleEndian</span><span class="sxs-lookup"><span data-stu-id="5fa4f-102">LittleEndian user defined type</span></span>

<span data-ttu-id="5fa4f-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5fa4f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5fa4f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fa4f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fa4f-105">Inscrivez-vous pour encoder un entier non signé dans l’ordre de primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="5fa4f-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="5fa4f-106">Le qubit avec l’index `0` encode le bit le plus bas d’un entier non signé.</span><span class="sxs-lookup"><span data-stu-id="5fa4f-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="5fa4f-107">Notes</span><span class="sxs-lookup"><span data-stu-id="5fa4f-107">Remarks</span></span>

<span data-ttu-id="5fa4f-108">Nous `LittleEndian` l’abrégeons `LE` dans la documentation.</span><span class="sxs-lookup"><span data-stu-id="5fa4f-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>