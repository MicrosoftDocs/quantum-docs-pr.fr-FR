---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: feb5da771ee6cb6a750fa76f9ffd8f5a3e0b5734
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840051"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="8e07b-102">UncurriedOpA fonction)</span><span class="sxs-lookup"><span data-stu-id="8e07b-102">UncurriedOpA function</span></span>

<span data-ttu-id="8e07b-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8e07b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8e07b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e07b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e07b-105">À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.</span><span class="sxs-lookup"><span data-stu-id="8e07b-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="8e07b-106">Le modificateur `A` indique que les opérations sont adjointable.</span><span class="sxs-lookup"><span data-stu-id="8e07b-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="8e07b-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="8e07b-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="8e07b-108">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="8e07b-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8e07b-109">Fonction qui retourne des opérations.</span><span class="sxs-lookup"><span data-stu-id="8e07b-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="8e07b-110">Sortie : ('t, 'U) => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="8e07b-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8e07b-111">Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="8e07b-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8e07b-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="8e07b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8e07b-113">Peut</span><span class="sxs-lookup"><span data-stu-id="8e07b-113">'T</span></span>

<span data-ttu-id="8e07b-114">Type du premier argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="8e07b-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="8e07b-115">'U</span><span class="sxs-lookup"><span data-stu-id="8e07b-115">'U</span></span>

<span data-ttu-id="8e07b-116">Type du deuxième argument d’une fonction curryfiée.</span><span class="sxs-lookup"><span data-stu-id="8e07b-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e07b-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e07b-117">See Also</span></span>

- [<span data-ttu-id="8e07b-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="8e07b-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)