---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: a26cc178f67fd99324355ac230d9e91081b6e238
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204927"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="4758c-102">TransformedOperation fonction)</span><span class="sxs-lookup"><span data-stu-id="4758c-102">TransformedOperation function</span></span>

<span data-ttu-id="4758c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4758c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4758c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4758c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4758c-105">À partir d’une fonction et d’une opération, retourne une nouvelle opération dont l’entrée est transformée par la fonction donnée.</span><span class="sxs-lookup"><span data-stu-id="4758c-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="4758c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4758c-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="4758c-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="4758c-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="4758c-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="4758c-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="4758c-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4758c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4758c-110">Opération à transformer.</span><span class="sxs-lookup"><span data-stu-id="4758c-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="4758c-111">Sortie : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4758c-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4758c-112">Une nouvelle opération tbat appelle `fn` avec son entrée, puis passe la sortie obtenue à `op` .</span><span class="sxs-lookup"><span data-stu-id="4758c-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4758c-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4758c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4758c-114">Peut</span><span class="sxs-lookup"><span data-stu-id="4758c-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="4758c-115">'U</span><span class="sxs-lookup"><span data-stu-id="4758c-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="4758c-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4758c-116">See Also</span></span>

- [<span data-ttu-id="4758c-117">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="4758c-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="4758c-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="4758c-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="4758c-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="4758c-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="4758c-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="4758c-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="4758c-121">Microsoft. Quantum. Canon. composed</span><span class="sxs-lookup"><span data-stu-id="4758c-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)