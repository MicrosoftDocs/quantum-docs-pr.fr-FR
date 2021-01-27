---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fac0fb6e03dc515892783fb4a5fa9cfc274550b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840142"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="784e1-102">TransformedOperationA fonction)</span><span class="sxs-lookup"><span data-stu-id="784e1-102">TransformedOperationA function</span></span>

<span data-ttu-id="784e1-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="784e1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="784e1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="784e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="784e1-105">À partir d’une fonction et d’une opération, retourne une nouvelle opération dont l’entrée est transformée par la fonction donnée.</span><span class="sxs-lookup"><span data-stu-id="784e1-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="784e1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="784e1-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="784e1-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="784e1-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="784e1-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="784e1-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="784e1-109">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="784e1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="784e1-110">Opération à transformer.</span><span class="sxs-lookup"><span data-stu-id="784e1-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj"></a><span data-ttu-id="784e1-111">Sortie : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="784e1-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="784e1-112">Une nouvelle opération tbat appelle `fn` avec son entrée, puis passe la sortie obtenue à `op` .</span><span class="sxs-lookup"><span data-stu-id="784e1-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="784e1-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="784e1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="784e1-114">Peut</span><span class="sxs-lookup"><span data-stu-id="784e1-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="784e1-115">'U</span><span class="sxs-lookup"><span data-stu-id="784e1-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="784e1-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="784e1-116">Example</span></span>

<span data-ttu-id="784e1-117">L’appel suivant utilise @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" pour transformer une opération conçue pour des @"Microsoft.Quantum.Arithmetic.BigEndian" entrées dans une opération qui accepte des entrées de type @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="784e1-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="784e1-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="784e1-118">See Also</span></span>

- [<span data-ttu-id="784e1-119">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="784e1-119">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="784e1-120">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="784e1-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="784e1-121">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="784e1-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="784e1-122">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="784e1-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="784e1-123">Microsoft. Quantum. Canon. composed</span><span class="sxs-lookup"><span data-stu-id="784e1-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)