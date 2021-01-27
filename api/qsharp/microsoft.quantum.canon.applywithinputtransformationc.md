---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Opération ApplyWithInputTransformationC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d877fedbc0caa1a9ebc87d80cbce9ab54ca20d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850355"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="f63ef-102">Opération ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="f63ef-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="f63ef-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f63ef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f63ef-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f63ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f63ef-105">Dans le cas d’une opération qui accepte une entrée, une fonction qui retourne une sortie compatible avec cette opération, et une entrée à cette fonction, applique l’opération à l’aide de la fonction pour transformer l’entrée en un formulaire attendu par l’opération.</span><span class="sxs-lookup"><span data-stu-id="f63ef-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f63ef-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f63ef-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="f63ef-107">FN : 'U-> '</span><span class="sxs-lookup"><span data-stu-id="f63ef-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="f63ef-108">Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.</span><span class="sxs-lookup"><span data-stu-id="f63ef-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f63ef-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="f63ef-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f63ef-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="f63ef-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="f63ef-111">entrée : 'U</span><span class="sxs-lookup"><span data-stu-id="f63ef-111">input : 'U</span></span>

<span data-ttu-id="f63ef-112">Entrée de la fonction.</span><span class="sxs-lookup"><span data-stu-id="f63ef-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f63ef-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f63ef-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f63ef-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="f63ef-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f63ef-115">Peut</span><span class="sxs-lookup"><span data-stu-id="f63ef-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="f63ef-116">'U</span><span class="sxs-lookup"><span data-stu-id="f63ef-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="f63ef-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="f63ef-117">Example</span></span>

<span data-ttu-id="f63ef-118">L’appel suivant utilise @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" pour appliquer une opération conçue pour des @"Microsoft.Quantum.Arithmetic.BigEndian" entrées à une entrée de type @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="f63ef-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="f63ef-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f63ef-119">See Also</span></span>

- [<span data-ttu-id="f63ef-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="f63ef-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="f63ef-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="f63ef-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="f63ef-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="f63ef-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="f63ef-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="f63ef-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)