---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Opération ApplyWithInputTransformation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3586e9a114a550fb1989186e9c18fe4f344cf060
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217184"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="9224a-102">Opération ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="9224a-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="9224a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9224a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9224a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9224a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9224a-105">Dans le cas d’une opération qui accepte une entrée, une fonction qui retourne une sortie compatible avec cette opération, et une entrée à cette fonction, applique l’opération à l’aide de la fonction pour transformer l’entrée en un formulaire attendu par l’opération.</span><span class="sxs-lookup"><span data-stu-id="9224a-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="9224a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9224a-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="9224a-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="9224a-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="9224a-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="9224a-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="9224a-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9224a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9224a-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="9224a-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="9224a-111">entrée : 'U</span><span class="sxs-lookup"><span data-stu-id="9224a-111">input : 'U</span></span>

<span data-ttu-id="9224a-112">Entrée de la fonction.</span><span class="sxs-lookup"><span data-stu-id="9224a-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9224a-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9224a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9224a-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9224a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9224a-115">Peut</span><span class="sxs-lookup"><span data-stu-id="9224a-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="9224a-116">'U</span><span class="sxs-lookup"><span data-stu-id="9224a-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="9224a-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9224a-117">See Also</span></span>

- [<span data-ttu-id="9224a-118">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="9224a-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="9224a-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="9224a-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="9224a-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="9224a-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="9224a-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="9224a-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)