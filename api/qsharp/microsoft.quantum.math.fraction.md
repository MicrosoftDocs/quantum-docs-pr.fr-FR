---
uid: Microsoft.Quantum.Math.Fraction
title: Type de fraction défini par l’utilisateur
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210673"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="b4cd4-102">Type de fraction défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="b4cd4-102">Fraction user defined type</span></span>

<span data-ttu-id="b4cd4-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b4cd4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b4cd4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4cd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4cd4-105">Représente un nombre rationnel du formulaire `p/q` .</span><span class="sxs-lookup"><span data-stu-id="b4cd4-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="b4cd4-106">Integer `p` est le premier élément du tuple et `q` est le deuxième élément du tuple.</span><span class="sxs-lookup"><span data-stu-id="b4cd4-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="b4cd4-107">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="b4cd4-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="b4cd4-108">Numérateur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b4cd4-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b4cd4-109">Numérateur de la fraction.</span><span class="sxs-lookup"><span data-stu-id="b4cd4-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="b4cd4-110">Dénominateur : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b4cd4-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b4cd4-111">Dénominateur de la fraction/</span><span class="sxs-lookup"><span data-stu-id="b4cd4-111">Denominator of the fraction/</span></span>