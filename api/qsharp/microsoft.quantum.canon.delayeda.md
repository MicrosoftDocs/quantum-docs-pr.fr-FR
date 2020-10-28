---
uid: Microsoft.Quantum.Canon.DelayedA
title: Fonction retardée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704214"
---
# <a name="delayeda-function"></a><span data-ttu-id="2812a-102">Fonction retardée</span><span class="sxs-lookup"><span data-stu-id="2812a-102">DelayedA function</span></span>

<span data-ttu-id="2812a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2812a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2812a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2812a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2812a-105">Retourne une opération qui applique l’opération donnée avec l’argument donné.</span><span class="sxs-lookup"><span data-stu-id="2812a-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="2812a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2812a-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="2812a-107">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2812a-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2812a-108">Opération à appliquer à la suite de l’application de la valeur de retour</span><span class="sxs-lookup"><span data-stu-id="2812a-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="2812a-109">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="2812a-109">arg : 'T</span></span>

<span data-ttu-id="2812a-110">Entrée à laquelle l’opération `op` est appliquée.</span><span class="sxs-lookup"><span data-stu-id="2812a-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="2812a-111">Sortie : [Unit](xref:microsoft.quantum.lang-ref.unit) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) d’unité</span><span class="sxs-lookup"><span data-stu-id="2812a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2812a-112">Nouvelle opération qui s’applique `op` à l’entrée `arg`</span><span class="sxs-lookup"><span data-stu-id="2812a-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2812a-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2812a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2812a-114">Peut</span><span class="sxs-lookup"><span data-stu-id="2812a-114">'T</span></span>

<span data-ttu-id="2812a-115">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="2812a-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2812a-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2812a-116">See Also</span></span>

- [<span data-ttu-id="2812a-117">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="2812a-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="2812a-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="2812a-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)