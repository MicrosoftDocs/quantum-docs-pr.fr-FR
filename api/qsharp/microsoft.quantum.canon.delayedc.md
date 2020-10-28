---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704195"
---
# <a name="delayedc-function"></a><span data-ttu-id="4dfd6-102">DelayedC fonction)</span><span class="sxs-lookup"><span data-stu-id="4dfd6-102">DelayedC function</span></span>

<span data-ttu-id="4dfd6-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4dfd6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4dfd6-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4dfd6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4dfd6-105">Retourne une opération qui applique l’opération donnée avec l’argument donné.</span><span class="sxs-lookup"><span data-stu-id="4dfd6-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="4dfd6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4dfd6-106">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="4dfd6-107">OP : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dfd6-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="4dfd6-108">Opération à appliquer à la suite de l’application de la valeur de retour</span><span class="sxs-lookup"><span data-stu-id="4dfd6-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="4dfd6-109">ARG : 't</span><span class="sxs-lookup"><span data-stu-id="4dfd6-109">arg : 'T</span></span>

<span data-ttu-id="4dfd6-110">Entrée à laquelle l’opération `op` est appliquée.</span><span class="sxs-lookup"><span data-stu-id="4dfd6-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl"></a><span data-ttu-id="4dfd6-111">Sortie : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="4dfd6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="4dfd6-112">Nouvelle opération qui s’applique `op` à l’entrée `arg`</span><span class="sxs-lookup"><span data-stu-id="4dfd6-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4dfd6-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4dfd6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4dfd6-114">Peut</span><span class="sxs-lookup"><span data-stu-id="4dfd6-114">'T</span></span>

<span data-ttu-id="4dfd6-115">Type d’entrée de l’opération à retarder.</span><span class="sxs-lookup"><span data-stu-id="4dfd6-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dfd6-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4dfd6-116">See Also</span></span>

- [<span data-ttu-id="4dfd6-117">Microsoft. Quantum. Canon. retardé</span><span class="sxs-lookup"><span data-stu-id="4dfd6-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="4dfd6-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="4dfd6-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)