---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fa204433dc8195dd27fa40980fb2262f8a3848bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204842"
---
# <a name="transformedoperationca-function"></a><span data-ttu-id="34c24-102">TransformedOperationCA fonction)</span><span class="sxs-lookup"><span data-stu-id="34c24-102">TransformedOperationCA function</span></span>

<span data-ttu-id="34c24-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="34c24-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="34c24-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34c24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34c24-105">À partir d’une fonction et d’une opération, retourne une nouvelle opération dont l’entrée est transformée par la fonction donnée.</span><span class="sxs-lookup"><span data-stu-id="34c24-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="34c24-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="34c24-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="34c24-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="34c24-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="34c24-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="34c24-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="34c24-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="34c24-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="34c24-110">Opération à transformer.</span><span class="sxs-lookup"><span data-stu-id="34c24-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj--ctl"></a><span data-ttu-id="34c24-111">Sortie : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="34c24-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="34c24-112">Une nouvelle opération tbat appelle `fn` avec son entrée, puis passe la sortie obtenue à `op` .</span><span class="sxs-lookup"><span data-stu-id="34c24-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="34c24-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="34c24-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="34c24-114">Peut</span><span class="sxs-lookup"><span data-stu-id="34c24-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="34c24-115">'U</span><span class="sxs-lookup"><span data-stu-id="34c24-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="34c24-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34c24-116">See Also</span></span>

- [<span data-ttu-id="34c24-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="34c24-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="34c24-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="34c24-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="34c24-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="34c24-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="34c24-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="34c24-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="34c24-121">Microsoft. Quantum. Canon. composed</span><span class="sxs-lookup"><span data-stu-id="34c24-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)