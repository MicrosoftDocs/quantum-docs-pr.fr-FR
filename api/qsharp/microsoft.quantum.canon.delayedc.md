---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207007"
---
# <a name="delayedc-function"></a><span data-ttu-id="336ae-102">DelayedC fonction)</span><span class="sxs-lookup"><span data-stu-id="336ae-102">DelayedC function</span></span>

<span data-ttu-id="336ae-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="336ae-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="336ae-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="336ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="336ae-105">Retourne une opération qui applique l’opération donnée avec l’argument donné.</span><span class="sxs-lookup"><span data-stu-id="336ae-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="336ae-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="336ae-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="336ae-107">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="336ae-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="336ae-108">Opération à appliquer à la suite de l’application de la valeur de retour</span><span class="sxs-lookup"><span data-stu-id="336ae-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="336ae-109">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="336ae-109">arg : 'T</span></span>

<span data-ttu-id="336ae-110">Entrée à laquelle l’opération `op` est appliquée.</span><span class="sxs-lookup"><span data-stu-id="336ae-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="336ae-111">Sortie : l’unité d' [unité](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) est CTL</span><span class="sxs-lookup"><span data-stu-id="336ae-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="336ae-112">Nouvelle opération qui s’applique `op` à l’entrée `arg`</span><span class="sxs-lookup"><span data-stu-id="336ae-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="336ae-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="336ae-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="336ae-114">Peut</span><span class="sxs-lookup"><span data-stu-id="336ae-114">'T</span></span>

<span data-ttu-id="336ae-115">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="336ae-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="336ae-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="336ae-116">See Also</span></span>

- [<span data-ttu-id="336ae-117">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="336ae-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="336ae-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="336ae-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)