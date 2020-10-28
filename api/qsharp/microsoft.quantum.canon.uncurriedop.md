---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703726"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="be19f-102">UncurriedOp fonction)</span><span class="sxs-lookup"><span data-stu-id="be19f-102">UncurriedOp function</span></span>

<span data-ttu-id="be19f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be19f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be19f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be19f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be19f-105">À partir d’une fonction qui retourne des opérations, retourne une nouvelle opération qui accepte les deux entrées en tant que Tuple.</span><span class="sxs-lookup"><span data-stu-id="be19f-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="be19f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="be19f-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="be19f-107">curriedOp : > 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be19f-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="be19f-108">Fonction qui retourne des opérations.</span><span class="sxs-lookup"><span data-stu-id="be19f-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="be19f-109">Sortie : ('t, 'U) => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be19f-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="be19f-110">Nouvelle opération `op` qui `op(t, u)` est équivalente à `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="be19f-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="be19f-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="be19f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be19f-112">Peut</span><span class="sxs-lookup"><span data-stu-id="be19f-112">'T</span></span>

<span data-ttu-id="be19f-113">Type de la première entrée d’une opération curryfiée.</span><span class="sxs-lookup"><span data-stu-id="be19f-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="be19f-114">'U</span><span class="sxs-lookup"><span data-stu-id="be19f-114">'U</span></span>

<span data-ttu-id="be19f-115">Type de la deuxième entrée d’une opération curryfiée.</span><span class="sxs-lookup"><span data-stu-id="be19f-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="be19f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="be19f-116">See Also</span></span>

- [<span data-ttu-id="be19f-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="be19f-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="be19f-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="be19f-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="be19f-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="be19f-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)