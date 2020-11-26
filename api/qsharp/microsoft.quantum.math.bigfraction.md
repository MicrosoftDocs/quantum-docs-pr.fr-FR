---
uid: Microsoft.Quantum.Math.BigFraction
title: Type défini par l’utilisateur BigFraction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211081"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="ba3cd-102">Type défini par l’utilisateur BigFraction</span><span class="sxs-lookup"><span data-stu-id="ba3cd-102">BigFraction user defined type</span></span>

<span data-ttu-id="ba3cd-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ba3cd-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ba3cd-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba3cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba3cd-105">Représente un nombre rationnel du formulaire `p/q` .</span><span class="sxs-lookup"><span data-stu-id="ba3cd-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="ba3cd-106">Integer `p` est le premier élément du tuple et `q` est le deuxième élément du tuple.</span><span class="sxs-lookup"><span data-stu-id="ba3cd-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="ba3cd-107">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="ba3cd-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="ba3cd-108">Numérateur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ba3cd-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ba3cd-109">Numérateur de la fraction.</span><span class="sxs-lookup"><span data-stu-id="ba3cd-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="ba3cd-110">Dénominateur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ba3cd-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ba3cd-111">Dénominateur de la fraction/</span><span class="sxs-lookup"><span data-stu-id="ba3cd-111">Denominator of the fraction/</span></span>