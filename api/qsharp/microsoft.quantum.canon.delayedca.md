---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704198"
---
# <a name="delayedca-function"></a><span data-ttu-id="a34c2-102">DelayedCA fonction)</span><span class="sxs-lookup"><span data-stu-id="a34c2-102">DelayedCA function</span></span>

<span data-ttu-id="a34c2-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a34c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a34c2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a34c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a34c2-105">Retourne une opération qui applique l’opération donnée avec l’argument donné.</span><span class="sxs-lookup"><span data-stu-id="a34c2-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="a34c2-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a34c2-106">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="a34c2-107">OP : 't => d' [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="a34c2-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="a34c2-108">Opération à appliquer à la suite de l’application de la valeur de retour</span><span class="sxs-lookup"><span data-stu-id="a34c2-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="a34c2-109">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="a34c2-109">arg : 'T</span></span>

<span data-ttu-id="a34c2-110">Entrée à laquelle l’opération `op` est appliquée.</span><span class="sxs-lookup"><span data-stu-id="a34c2-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl--adj"></a><span data-ttu-id="a34c2-111">Sortie : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="a34c2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="a34c2-112">Nouvelle opération qui s’applique `op` à l’entrée `arg`</span><span class="sxs-lookup"><span data-stu-id="a34c2-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a34c2-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a34c2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a34c2-114">Peut</span><span class="sxs-lookup"><span data-stu-id="a34c2-114">'T</span></span>

<span data-ttu-id="a34c2-115">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="a34c2-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a34c2-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a34c2-116">See Also</span></span>

- [<span data-ttu-id="a34c2-117">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="a34c2-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="a34c2-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="a34c2-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)