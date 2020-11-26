---
uid: Microsoft.Quantum.Canon.DelayedA
title: Fonction retardée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 33ff4dab36a6c6e17b9496a623f70b814c9f2fed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207069"
---
# <a name="delayeda-function"></a><span data-ttu-id="14b70-102">Fonction retardée</span><span class="sxs-lookup"><span data-stu-id="14b70-102">DelayedA function</span></span>

<span data-ttu-id="14b70-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14b70-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14b70-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14b70-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14b70-105">Retourne une opération qui applique l’opération donnée avec l’argument donné.</span><span class="sxs-lookup"><span data-stu-id="14b70-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="14b70-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="14b70-106">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="14b70-107">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="14b70-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="14b70-108">Opération à appliquer à la suite de l’application de la valeur de retour</span><span class="sxs-lookup"><span data-stu-id="14b70-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="14b70-109">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="14b70-109">arg : 'T</span></span>

<span data-ttu-id="14b70-110">Entrée à laquelle l’opération `op` est appliquée.</span><span class="sxs-lookup"><span data-stu-id="14b70-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj"></a><span data-ttu-id="14b70-111">Sortie : l’unité d' [unité](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) est adj</span><span class="sxs-lookup"><span data-stu-id="14b70-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="14b70-112">Nouvelle opération qui s’applique `op` à l’entrée `arg`</span><span class="sxs-lookup"><span data-stu-id="14b70-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="14b70-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="14b70-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="14b70-114">Peut</span><span class="sxs-lookup"><span data-stu-id="14b70-114">'T</span></span>

<span data-ttu-id="14b70-115">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="14b70-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="14b70-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14b70-116">See Also</span></span>

- [<span data-ttu-id="14b70-117">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="14b70-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="14b70-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="14b70-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)