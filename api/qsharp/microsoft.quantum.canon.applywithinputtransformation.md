---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Opération ApplyWithInputTransformation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704566"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="7ad67-102">Opération ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="7ad67-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="7ad67-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7ad67-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7ad67-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7ad67-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7ad67-105">Dans le cas d’une opération qui accepte une entrée, une fonction qui retourne une sortie compatible avec cette opération, et une entrée à cette fonction, applique l’opération à l’aide de la fonction pour transformer l’entrée en un formulaire attendu par l’opération.</span><span class="sxs-lookup"><span data-stu-id="7ad67-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="7ad67-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7ad67-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="7ad67-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="7ad67-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="7ad67-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="7ad67-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="7ad67-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ad67-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7ad67-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="7ad67-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="7ad67-111">entrée : 'U</span><span class="sxs-lookup"><span data-stu-id="7ad67-111">input : 'U</span></span>

<span data-ttu-id="7ad67-112">Entrée de la fonction.</span><span class="sxs-lookup"><span data-stu-id="7ad67-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7ad67-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ad67-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7ad67-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7ad67-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7ad67-115">Peut</span><span class="sxs-lookup"><span data-stu-id="7ad67-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="7ad67-116">'U</span><span class="sxs-lookup"><span data-stu-id="7ad67-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="7ad67-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7ad67-117">See Also</span></span>

- [<span data-ttu-id="7ad67-118">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="7ad67-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="7ad67-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="7ad67-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="7ad67-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="7ad67-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="7ad67-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="7ad67-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)