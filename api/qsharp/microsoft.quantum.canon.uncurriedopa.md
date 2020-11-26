---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204621"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="c7c28-102">UncurriedOpA fonction)</span><span class="sxs-lookup"><span data-stu-id="c7c28-102">UncurriedOpA function</span></span>

<span data-ttu-id="c7c28-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7c28-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7c28-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c7c28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c7c28-105">À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.</span><span class="sxs-lookup"><span data-stu-id="c7c28-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="c7c28-106">Le modificateur `A` indique que les opérations sont adjointable.</span><span class="sxs-lookup"><span data-stu-id="c7c28-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="c7c28-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="c7c28-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="c7c28-108">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="c7c28-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c7c28-109">Fonction qui retourne des opérations.</span><span class="sxs-lookup"><span data-stu-id="c7c28-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="c7c28-110">Sortie : ('t, 'U) => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="c7c28-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c7c28-111">Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="c7c28-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c7c28-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c7c28-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c7c28-113">Peut</span><span class="sxs-lookup"><span data-stu-id="c7c28-113">'T</span></span>

<span data-ttu-id="c7c28-114">Type du premier argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="c7c28-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="c7c28-115">'U</span><span class="sxs-lookup"><span data-stu-id="c7c28-115">'U</span></span>

<span data-ttu-id="c7c28-116">Type du deuxième argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="c7c28-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7c28-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7c28-117">See Also</span></span>

- [<span data-ttu-id="c7c28-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="c7c28-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)