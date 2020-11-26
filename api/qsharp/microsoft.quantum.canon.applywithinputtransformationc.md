---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Opération ApplyWithInputTransformationC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 030c41d3ce0a5d613a95c6511f7278497ec5cda1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217167"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="9e39e-102">Opération ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="9e39e-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="9e39e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9e39e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9e39e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e39e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e39e-105">Dans le cas d’une opération qui accepte une entrée, une fonction qui retourne une sortie compatible avec cette opération, et une entrée à cette fonction, applique l’opération à l’aide de la fonction pour transformer l’entrée en un formulaire attendu par l’opération.</span><span class="sxs-lookup"><span data-stu-id="9e39e-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="9e39e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9e39e-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="9e39e-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="9e39e-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="9e39e-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="9e39e-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="9e39e-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="9e39e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="9e39e-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="9e39e-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="9e39e-111">entrée : 'U</span><span class="sxs-lookup"><span data-stu-id="9e39e-111">input : 'U</span></span>

<span data-ttu-id="9e39e-112">Entrée de la fonction.</span><span class="sxs-lookup"><span data-stu-id="9e39e-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e39e-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e39e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9e39e-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9e39e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9e39e-115">Peut</span><span class="sxs-lookup"><span data-stu-id="9e39e-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="9e39e-116">'U</span><span class="sxs-lookup"><span data-stu-id="9e39e-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="9e39e-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e39e-117">See Also</span></span>

- [<span data-ttu-id="9e39e-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="9e39e-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="9e39e-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="9e39e-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="9e39e-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="9e39e-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="9e39e-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="9e39e-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)