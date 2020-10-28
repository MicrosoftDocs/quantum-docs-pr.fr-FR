---
uid: Microsoft.Quantum.Math.BigFraction
title: Type défini par l’utilisateur BigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708312"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="ad925-102">Type défini par l’utilisateur BigFraction</span><span class="sxs-lookup"><span data-stu-id="ad925-102">BigFraction user defined type</span></span>

<span data-ttu-id="ad925-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ad925-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ad925-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad925-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad925-105">Représente un nombre rationnel du formulaire `p/q` .</span><span class="sxs-lookup"><span data-stu-id="ad925-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="ad925-106">Integer `p` est le premier élément du tuple et `q` est le deuxième élément du tuple.</span><span class="sxs-lookup"><span data-stu-id="ad925-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="ad925-107">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="ad925-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="ad925-108">Numérateur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ad925-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ad925-109">Numérateur de la fraction.</span><span class="sxs-lookup"><span data-stu-id="ad925-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="ad925-110">Dénominateur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ad925-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ad925-111">Dénominateur de la fraction/</span><span class="sxs-lookup"><span data-stu-id="ad925-111">Denominator of the fraction/</span></span>