---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840038"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="68fd6-102">UncurriedOpCA fonction)</span><span class="sxs-lookup"><span data-stu-id="68fd6-102">UncurriedOpCA function</span></span>

<span data-ttu-id="68fd6-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="68fd6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="68fd6-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68fd6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68fd6-105">À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.</span><span class="sxs-lookup"><span data-stu-id="68fd6-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="68fd6-106">Le modificateur `CA` indique que les opérations sont contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="68fd6-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="68fd6-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="68fd6-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="68fd6-108">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="68fd6-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="68fd6-109">Fonction qui retourne des opérations.</span><span class="sxs-lookup"><span data-stu-id="68fd6-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="68fd6-110">Sortie : ('t, 'U) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="68fd6-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="68fd6-111">Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="68fd6-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="68fd6-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="68fd6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68fd6-113">Peut</span><span class="sxs-lookup"><span data-stu-id="68fd6-113">'T</span></span>

<span data-ttu-id="68fd6-114">Type du premier argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="68fd6-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="68fd6-115">'U</span><span class="sxs-lookup"><span data-stu-id="68fd6-115">'U</span></span>

<span data-ttu-id="68fd6-116">Type du deuxième argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="68fd6-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="68fd6-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68fd6-117">See Also</span></span>

- [<span data-ttu-id="68fd6-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="68fd6-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)