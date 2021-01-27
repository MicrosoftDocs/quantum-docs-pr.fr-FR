---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852055"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="07a6f-102">TransformedOperation fonction)</span><span class="sxs-lookup"><span data-stu-id="07a6f-102">TransformedOperation function</span></span>

<span data-ttu-id="07a6f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="07a6f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="07a6f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="07a6f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="07a6f-105">À partir d’une fonction et d’une opération, retourne une nouvelle opération dont l’entrée est transformée par la fonction donnée.</span><span class="sxs-lookup"><span data-stu-id="07a6f-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="07a6f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="07a6f-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="07a6f-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="07a6f-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="07a6f-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="07a6f-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="07a6f-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07a6f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="07a6f-110">Opération à transformer.</span><span class="sxs-lookup"><span data-stu-id="07a6f-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="07a6f-111">Sortie : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07a6f-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="07a6f-112">Une nouvelle opération tbat appelle `fn` avec son entrée, puis passe la sortie obtenue à `op` .</span><span class="sxs-lookup"><span data-stu-id="07a6f-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="07a6f-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="07a6f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="07a6f-114">Peut</span><span class="sxs-lookup"><span data-stu-id="07a6f-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="07a6f-115">'U</span><span class="sxs-lookup"><span data-stu-id="07a6f-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="07a6f-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="07a6f-116">Example</span></span>

<span data-ttu-id="07a6f-117">L’appel suivant utilise @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" pour transformer une opération conçue pour des @"Microsoft.Quantum.Arithmetic.BigEndian" entrées dans une opération qui accepte des entrées de type @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="07a6f-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="07a6f-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07a6f-118">See Also</span></span>

- [<span data-ttu-id="07a6f-119">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="07a6f-119">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="07a6f-120">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="07a6f-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="07a6f-121">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="07a6f-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="07a6f-122">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="07a6f-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="07a6f-123">Microsoft. Quantum. Canon. composed</span><span class="sxs-lookup"><span data-stu-id="07a6f-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)