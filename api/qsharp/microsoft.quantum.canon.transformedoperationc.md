---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 964576788bc80dd8920acdfb62d5d69a060e75f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204859"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="3242e-102">TransformedOperationC fonction)</span><span class="sxs-lookup"><span data-stu-id="3242e-102">TransformedOperationC function</span></span>

<span data-ttu-id="3242e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3242e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3242e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3242e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3242e-105">À partir d’une fonction et d’une opération, retourne une nouvelle opération dont l’entrée est transformée par la fonction donnée.</span><span class="sxs-lookup"><span data-stu-id="3242e-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="3242e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3242e-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="3242e-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="3242e-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="3242e-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="3242e-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="3242e-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="3242e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3242e-110">Opération à transformer.</span><span class="sxs-lookup"><span data-stu-id="3242e-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-ctl"></a><span data-ttu-id="3242e-111">Sortie : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="3242e-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3242e-112">Une nouvelle opération tbat appelle `fn` avec son entrée, puis passe la sortie obtenue à `op` .</span><span class="sxs-lookup"><span data-stu-id="3242e-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3242e-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="3242e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3242e-114">Peut</span><span class="sxs-lookup"><span data-stu-id="3242e-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="3242e-115">'U</span><span class="sxs-lookup"><span data-stu-id="3242e-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="3242e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3242e-116">See Also</span></span>

- [<span data-ttu-id="3242e-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="3242e-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="3242e-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="3242e-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="3242e-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="3242e-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="3242e-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="3242e-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="3242e-121">Microsoft. Quantum. Canon. composed</span><span class="sxs-lookup"><span data-stu-id="3242e-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)