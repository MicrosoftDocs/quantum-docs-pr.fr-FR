---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: fe2babb87d716185286b0864745f7ff6e637f8a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207006"
---
# <a name="delayedca-function"></a><span data-ttu-id="e085e-102">DelayedCA fonction)</span><span class="sxs-lookup"><span data-stu-id="e085e-102">DelayedCA function</span></span>

<span data-ttu-id="e085e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e085e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e085e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e085e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e085e-105">Retourne une opération qui applique l’opération donnée avec l’argument donné.</span><span class="sxs-lookup"><span data-stu-id="e085e-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="e085e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e085e-106">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="e085e-107">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="e085e-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e085e-108">Opération à appliquer à la suite de l’application de la valeur de retour</span><span class="sxs-lookup"><span data-stu-id="e085e-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="e085e-109">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="e085e-109">arg : 'T</span></span>

<span data-ttu-id="e085e-110">Entrée à laquelle l’opération `op` est appliquée.</span><span class="sxs-lookup"><span data-stu-id="e085e-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj--ctl"></a><span data-ttu-id="e085e-111">Sortie : l’unité d' [unité](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="e085e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e085e-112">Nouvelle opération qui s’applique `op` à l’entrée `arg`</span><span class="sxs-lookup"><span data-stu-id="e085e-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e085e-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e085e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e085e-114">Peut</span><span class="sxs-lookup"><span data-stu-id="e085e-114">'T</span></span>

<span data-ttu-id="e085e-115">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="e085e-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e085e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e085e-116">See Also</span></span>

- [<span data-ttu-id="e085e-117">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="e085e-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="e085e-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="e085e-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)