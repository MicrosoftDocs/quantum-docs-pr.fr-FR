---
uid: Microsoft.Quantum.Math.Fraction
title: Type de fraction défini par l’utilisateur
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857515"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="e96cf-102">Type de fraction défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="e96cf-102">Fraction user defined type</span></span>

<span data-ttu-id="e96cf-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e96cf-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e96cf-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e96cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e96cf-105">Représente un nombre rationnel du formulaire `p/q` .</span><span class="sxs-lookup"><span data-stu-id="e96cf-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="e96cf-106">Integer `p` est le premier élément du tuple et `q` est le deuxième élément du tuple.</span><span class="sxs-lookup"><span data-stu-id="e96cf-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="e96cf-107">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="e96cf-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="e96cf-108">Numérateur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e96cf-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e96cf-109">Numérateur de la fraction.</span><span class="sxs-lookup"><span data-stu-id="e96cf-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="e96cf-110">Dénominateur : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e96cf-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e96cf-111">Dénominateur de la fraction/</span><span class="sxs-lookup"><span data-stu-id="e96cf-111">Denominator of the fraction/</span></span>