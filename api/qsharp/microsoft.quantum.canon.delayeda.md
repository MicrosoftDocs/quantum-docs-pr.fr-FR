---
uid: Microsoft.Quantum.Canon.DelayedA
title: Fonction retardée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: e53279bd3ddc5fa8bc0c862f998b273a9e17a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840595"
---
# <a name="delayeda-function"></a><span data-ttu-id="3987c-102">Fonction retardée</span><span class="sxs-lookup"><span data-stu-id="3987c-102">DelayedA function</span></span>

<span data-ttu-id="3987c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3987c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3987c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3987c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3987c-105">Retourne une opération qui applique l’opération donnée avec l’argument donné.</span><span class="sxs-lookup"><span data-stu-id="3987c-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="3987c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3987c-106">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="3987c-107">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="3987c-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3987c-108">Opération à appliquer à la suite de l’application de la valeur de retour</span><span class="sxs-lookup"><span data-stu-id="3987c-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="3987c-109">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="3987c-109">arg : 'T</span></span>

<span data-ttu-id="3987c-110">Entrée à laquelle l’opération `op` est appliquée.</span><span class="sxs-lookup"><span data-stu-id="3987c-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj"></a><span data-ttu-id="3987c-111">Sortie : l’unité d' [unité](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) est adj</span><span class="sxs-lookup"><span data-stu-id="3987c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3987c-112">Nouvelle opération qui s’applique `op` à l’entrée `arg`</span><span class="sxs-lookup"><span data-stu-id="3987c-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3987c-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="3987c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3987c-114">Peut</span><span class="sxs-lookup"><span data-stu-id="3987c-114">'T</span></span>

<span data-ttu-id="3987c-115">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="3987c-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="3987c-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3987c-116">See Also</span></span>

- [<span data-ttu-id="3987c-117">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="3987c-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="3987c-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="3987c-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)