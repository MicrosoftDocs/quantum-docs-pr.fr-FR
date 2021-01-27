---
uid: Microsoft.Quantum.Convert.Call
title: Opération d’appel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850209"
---
# <a name="call-operation"></a><span data-ttu-id="78210-102">Opération d’appel</span><span class="sxs-lookup"><span data-stu-id="78210-102">Call operation</span></span>

<span data-ttu-id="78210-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="78210-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="78210-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78210-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78210-105">Appelle une fonction avec une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="78210-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="78210-106">Description</span><span class="sxs-lookup"><span data-stu-id="78210-106">Description</span></span>

<span data-ttu-id="78210-107">À partir d’une fonction et d’une entrée de cette fonction, appelle la fonction et retourne sa sortie.</span><span class="sxs-lookup"><span data-stu-id="78210-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="78210-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="78210-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="78210-109">FN : sortie’Input-> '</span><span class="sxs-lookup"><span data-stu-id="78210-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="78210-110">Fonction à appeler.</span><span class="sxs-lookup"><span data-stu-id="78210-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="78210-111">entrée : 'Input</span><span class="sxs-lookup"><span data-stu-id="78210-111">input : 'Input</span></span>

<span data-ttu-id="78210-112">Entrée à passer à la fonction.</span><span class="sxs-lookup"><span data-stu-id="78210-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="78210-113">Sortie : 'Output</span><span class="sxs-lookup"><span data-stu-id="78210-113">Output : 'Output</span></span>

<span data-ttu-id="78210-114">Résultat de l’appel de `fn`.</span><span class="sxs-lookup"><span data-stu-id="78210-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="78210-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="78210-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="78210-116">'Entrée</span><span class="sxs-lookup"><span data-stu-id="78210-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="78210-117">'Sortie</span><span class="sxs-lookup"><span data-stu-id="78210-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="78210-118">Notes</span><span class="sxs-lookup"><span data-stu-id="78210-118">Remarks</span></span>

<span data-ttu-id="78210-119">Cette opération est principalement utile pour forcer l’appel d’une fonction à un emplacement spécifique au sein d’une opération, ou pour appeler une fonction dans laquelle une opération est attendue.</span><span class="sxs-lookup"><span data-stu-id="78210-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>