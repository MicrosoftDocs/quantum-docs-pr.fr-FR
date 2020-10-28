---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703711"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="be2bd-102">UncurriedOpCA fonction)</span><span class="sxs-lookup"><span data-stu-id="be2bd-102">UncurriedOpCA function</span></span>

<span data-ttu-id="be2bd-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be2bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be2bd-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be2bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be2bd-105">À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.</span><span class="sxs-lookup"><span data-stu-id="be2bd-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="be2bd-106">Le modificateur `CA` indique que les opérations sont contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="be2bd-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="be2bd-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="be2bd-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="be2bd-108">curriedOp : 't-> 'U => d' [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="be2bd-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="be2bd-109">Fonction qui retourne des opérations.</span><span class="sxs-lookup"><span data-stu-id="be2bd-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl--adj"></a><span data-ttu-id="be2bd-110">Sortie : ('t, 'U) => d' [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="be2bd-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="be2bd-111">Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="be2bd-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="be2bd-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="be2bd-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be2bd-113">Peut</span><span class="sxs-lookup"><span data-stu-id="be2bd-113">'T</span></span>

<span data-ttu-id="be2bd-114">Type du premier argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="be2bd-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="be2bd-115">'U</span><span class="sxs-lookup"><span data-stu-id="be2bd-115">'U</span></span>

<span data-ttu-id="be2bd-116">Type du deuxième argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="be2bd-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="be2bd-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="be2bd-117">See Also</span></span>

- [<span data-ttu-id="be2bd-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="be2bd-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)