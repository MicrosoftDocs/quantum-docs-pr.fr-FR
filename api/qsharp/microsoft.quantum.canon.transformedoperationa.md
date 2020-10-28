---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 349424a102dba7354bbaa65fffdc2b5d506a3b91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703765"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="5355e-102">TransformedOperationA fonction)</span><span class="sxs-lookup"><span data-stu-id="5355e-102">TransformedOperationA function</span></span>

<span data-ttu-id="5355e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5355e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5355e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5355e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5355e-105">À partir d’une fonction et d’une opération, retourne une nouvelle opération dont l’entrée est transformée par la fonction donnée.</span><span class="sxs-lookup"><span data-stu-id="5355e-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="5355e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="5355e-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="5355e-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="5355e-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="5355e-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="5355e-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="5355e-109">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5355e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="5355e-110">Opération à transformer.</span><span class="sxs-lookup"><span data-stu-id="5355e-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-adj"></a><span data-ttu-id="5355e-111">Sortie : 'U => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5355e-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="5355e-112">Une nouvelle opération tbat appelle `fn` avec son entrée, puis passe la sortie obtenue à `op` .</span><span class="sxs-lookup"><span data-stu-id="5355e-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5355e-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="5355e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5355e-114">Peut</span><span class="sxs-lookup"><span data-stu-id="5355e-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="5355e-115">'U</span><span class="sxs-lookup"><span data-stu-id="5355e-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="5355e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5355e-116">See Also</span></span>

- [<span data-ttu-id="5355e-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="5355e-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="5355e-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="5355e-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="5355e-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="5355e-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="5355e-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="5355e-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="5355e-121">Microsoft. Quantum. Canon. composed</span><span class="sxs-lookup"><span data-stu-id="5355e-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)