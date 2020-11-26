---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216623"
---
# <a name="curriedop-function"></a><span data-ttu-id="a8ab3-102">CurriedOp fonction)</span><span class="sxs-lookup"><span data-stu-id="a8ab3-102">CurriedOp function</span></span>

<span data-ttu-id="a8ab3-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8ab3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8ab3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8ab3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8ab3-105">Retourne une version curryfiée d’une opération sur deux entrées.</span><span class="sxs-lookup"><span data-stu-id="a8ab3-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="a8ab3-106">Autrement dit, étant donné une opération avec deux entrées, cette fonction applique $f isomorphism (x, y) \equiv f (x) (y) $ de l’expression de la valeur pour retourner une opération d’une entrée qui retourne une opération d’une entrée.</span><span class="sxs-lookup"><span data-stu-id="a8ab3-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="a8ab3-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="a8ab3-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="a8ab3-108">OP : ('t, 'U) => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8ab3-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a8ab3-109">Opération dont l’entrée est une paire.</span><span class="sxs-lookup"><span data-stu-id="a8ab3-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="a8ab3-110">Sortie : 't-> 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8ab3-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a8ab3-111">Opération qui accepte le premier élément d’une paire et retourne une opération qui accepte comme entrée le deuxième élément de l’entrée de l’opération d’origine.</span><span class="sxs-lookup"><span data-stu-id="a8ab3-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a8ab3-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a8ab3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8ab3-113">Peut</span><span class="sxs-lookup"><span data-stu-id="a8ab3-113">'T</span></span>

<span data-ttu-id="a8ab3-114">Type du premier composant d’une fonction défini sur les paires.</span><span class="sxs-lookup"><span data-stu-id="a8ab3-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="a8ab3-115">'U</span><span class="sxs-lookup"><span data-stu-id="a8ab3-115">'U</span></span>

<span data-ttu-id="a8ab3-116">Type du deuxième composant d’une fonction définie sur les paires.</span><span class="sxs-lookup"><span data-stu-id="a8ab3-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8ab3-117">Notes</span><span class="sxs-lookup"><span data-stu-id="a8ab3-117">Remarks</span></span>

<span data-ttu-id="a8ab3-118">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="a8ab3-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```