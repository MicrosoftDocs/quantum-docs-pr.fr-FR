---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204587"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="4934d-102">UncurriedOpC fonction)</span><span class="sxs-lookup"><span data-stu-id="4934d-102">UncurriedOpC function</span></span>

<span data-ttu-id="4934d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4934d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4934d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4934d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4934d-105">À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.</span><span class="sxs-lookup"><span data-stu-id="4934d-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="4934d-106">Le modificateur `C` indique que les opérations sont contrôlable.</span><span class="sxs-lookup"><span data-stu-id="4934d-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="4934d-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="4934d-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="4934d-108">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="4934d-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4934d-109">Fonction qui retourne des opérations.</span><span class="sxs-lookup"><span data-stu-id="4934d-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="4934d-110">Sortie : ('t, 'U) => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="4934d-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4934d-111">Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="4934d-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4934d-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4934d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4934d-113">Peut</span><span class="sxs-lookup"><span data-stu-id="4934d-113">'T</span></span>

<span data-ttu-id="4934d-114">Type du premier argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="4934d-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="4934d-115">'U</span><span class="sxs-lookup"><span data-stu-id="4934d-115">'U</span></span>

<span data-ttu-id="4934d-116">Type du deuxième argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="4934d-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="4934d-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4934d-117">See Also</span></span>

- [<span data-ttu-id="4934d-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="4934d-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)