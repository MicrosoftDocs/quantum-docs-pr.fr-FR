---
uid: Microsoft.Quantum.Canon.Delayed
title: Fonction retardée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840583"
---
# <a name="delayed-function"></a><span data-ttu-id="88ccd-102">Fonction retardée</span><span class="sxs-lookup"><span data-stu-id="88ccd-102">Delayed function</span></span>

<span data-ttu-id="88ccd-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="88ccd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="88ccd-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88ccd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88ccd-105">Retourne une opération qui applique l’opération donnée avec l’argument donné.</span><span class="sxs-lookup"><span data-stu-id="88ccd-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="88ccd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="88ccd-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="88ccd-107">OP : 't => 'U</span><span class="sxs-lookup"><span data-stu-id="88ccd-107">op : 'T => 'U</span></span> 

<span data-ttu-id="88ccd-108">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="88ccd-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="88ccd-109">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="88ccd-109">arg : 'T</span></span>

<span data-ttu-id="88ccd-110">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="88ccd-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="88ccd-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit) => 'U</span><span class="sxs-lookup"><span data-stu-id="88ccd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="88ccd-112">Nouvelle opération qui s’applique `op` à l’entrée `arg`</span><span class="sxs-lookup"><span data-stu-id="88ccd-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="88ccd-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="88ccd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="88ccd-114">Peut</span><span class="sxs-lookup"><span data-stu-id="88ccd-114">'T</span></span>

<span data-ttu-id="88ccd-115">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="88ccd-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="88ccd-116">'U</span><span class="sxs-lookup"><span data-stu-id="88ccd-116">'U</span></span>

<span data-ttu-id="88ccd-117">Type de retour de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="88ccd-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="88ccd-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88ccd-118">See Also</span></span>

- [<span data-ttu-id="88ccd-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="88ccd-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="88ccd-120">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="88ccd-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="88ccd-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="88ccd-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="88ccd-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="88ccd-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)