---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 21c9cdfc3b5b266cb3b93e52ee2fa4c655caf795
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703759"
---
# <a name="transformedoperationca-function"></a><span data-ttu-id="f26de-102">TransformedOperationCA fonction)</span><span class="sxs-lookup"><span data-stu-id="f26de-102">TransformedOperationCA function</span></span>

<span data-ttu-id="f26de-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f26de-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f26de-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f26de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f26de-105">À partir d’une fonction et d’une opération, retourne une nouvelle opération dont l’entrée est transformée par la fonction donnée.</span><span class="sxs-lookup"><span data-stu-id="f26de-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f26de-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f26de-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="f26de-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="f26de-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="f26de-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="f26de-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="f26de-109">OP : t [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="f26de-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f26de-110">Opération à transformer.</span><span class="sxs-lookup"><span data-stu-id="f26de-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-adj--ctl"></a><span data-ttu-id="f26de-111">Sortie : 'U => ajustable d' [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="f26de-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f26de-112">Une nouvelle opération tbat appelle `fn` avec son entrée, puis passe la sortie obtenue à `op` .</span><span class="sxs-lookup"><span data-stu-id="f26de-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f26de-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="f26de-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f26de-114">Peut</span><span class="sxs-lookup"><span data-stu-id="f26de-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="f26de-115">'U</span><span class="sxs-lookup"><span data-stu-id="f26de-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="f26de-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f26de-116">See Also</span></span>

- [<span data-ttu-id="f26de-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="f26de-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="f26de-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="f26de-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="f26de-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="f26de-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="f26de-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="f26de-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="f26de-121">Microsoft. Quantum. Canon. composed</span><span class="sxs-lookup"><span data-stu-id="f26de-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)