---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195373"
---
# <a name="inversemodi-function"></a><span data-ttu-id="86ea9-102">InverseModI fonction)</span><span class="sxs-lookup"><span data-stu-id="86ea9-102">InverseModI function</span></span>

<span data-ttu-id="86ea9-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="86ea9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="86ea9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86ea9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86ea9-105">Retourne $b $ de telle sorte que $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="86ea9-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="86ea9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="86ea9-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="86ea9-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="86ea9-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="86ea9-108">Nombre en cours d’inversion</span><span class="sxs-lookup"><span data-stu-id="86ea9-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="86ea9-109">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="86ea9-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="86ea9-110">Modulo en fonction duquel les nombres sont inversés</span><span class="sxs-lookup"><span data-stu-id="86ea9-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="86ea9-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="86ea9-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="86ea9-112">Entier $b $ de telle sorte que $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="86ea9-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>