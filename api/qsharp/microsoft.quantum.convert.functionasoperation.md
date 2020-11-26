---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224375"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="27df8-102">FunctionAsOperation fonction)</span><span class="sxs-lookup"><span data-stu-id="27df8-102">FunctionAsOperation function</span></span>

<span data-ttu-id="27df8-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="27df8-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="27df8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27df8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27df8-105">Convertit des fonctions en opérations.</span><span class="sxs-lookup"><span data-stu-id="27df8-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="27df8-106">Description</span><span class="sxs-lookup"><span data-stu-id="27df8-106">Description</span></span>

<span data-ttu-id="27df8-107">Pour une fonction donnée, retourne une opération qui appelle cette fonction et qui ne fait rien d’autre.</span><span class="sxs-lookup"><span data-stu-id="27df8-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="27df8-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="27df8-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="27df8-109">FN : sortie’Input-> '</span><span class="sxs-lookup"><span data-stu-id="27df8-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="27df8-110">Fonction à convertir en une opération.</span><span class="sxs-lookup"><span data-stu-id="27df8-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="27df8-111">Sortie : sortie’Input => '</span><span class="sxs-lookup"><span data-stu-id="27df8-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="27df8-112">Opération `op` qui `op(input)` est identique à `fn(input)` pour All `input` .</span><span class="sxs-lookup"><span data-stu-id="27df8-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="27df8-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="27df8-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="27df8-114">'Entrée</span><span class="sxs-lookup"><span data-stu-id="27df8-114">'Input</span></span>

<span data-ttu-id="27df8-115">Type d’entrée de la fonction à convertir.</span><span class="sxs-lookup"><span data-stu-id="27df8-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="27df8-116">'Sortie</span><span class="sxs-lookup"><span data-stu-id="27df8-116">'Output</span></span>

<span data-ttu-id="27df8-117">Type de sortie de la fonction à convertir.</span><span class="sxs-lookup"><span data-stu-id="27df8-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="27df8-118">Notes</span><span class="sxs-lookup"><span data-stu-id="27df8-118">Remarks</span></span>

<span data-ttu-id="27df8-119">Cela est principalement utile pour passer des fonctions à des fonctions ou des opérations qui attendent une opération comme entrée.</span><span class="sxs-lookup"><span data-stu-id="27df8-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>