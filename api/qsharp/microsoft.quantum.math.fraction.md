---
uid: Microsoft.Quantum.Math.Fraction
title: Type de fraction défini par l’utilisateur
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708504"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="13e89-102">Type de fraction défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="13e89-102">Fraction user defined type</span></span>

<span data-ttu-id="13e89-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="13e89-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="13e89-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13e89-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13e89-105">Représente un nombre rationnel du formulaire `p/q` .</span><span class="sxs-lookup"><span data-stu-id="13e89-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="13e89-106">Integer `p` est le premier élément du tuple et `q` est le deuxième élément du tuple.</span><span class="sxs-lookup"><span data-stu-id="13e89-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="13e89-107">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="13e89-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="13e89-108">Numérateur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13e89-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13e89-109">Numérateur de la fraction.</span><span class="sxs-lookup"><span data-stu-id="13e89-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="13e89-110">Dénominateur : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13e89-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13e89-111">Dénominateur de la fraction/</span><span class="sxs-lookup"><span data-stu-id="13e89-111">Denominator of the fraction/</span></span>