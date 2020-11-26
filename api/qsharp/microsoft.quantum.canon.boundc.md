---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207579"
---
# <a name="boundc-function"></a><span data-ttu-id="ba0fe-102">BoundC fonction)</span><span class="sxs-lookup"><span data-stu-id="ba0fe-102">BoundC function</span></span>

<span data-ttu-id="ba0fe-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ba0fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ba0fe-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba0fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba0fe-105">À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="ba0fe-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="ba0fe-106">Le modificateur `C` indique que toutes les opérations dans le tableau sont contrôlables.</span><span class="sxs-lookup"><span data-stu-id="ba0fe-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="ba0fe-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="ba0fe-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="ba0fe-108">opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL []</span><span class="sxs-lookup"><span data-stu-id="ba0fe-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="ba0fe-109">Séquence d’opérations à effectuer sur une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="ba0fe-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="ba0fe-110">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="ba0fe-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ba0fe-111">Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.</span><span class="sxs-lookup"><span data-stu-id="ba0fe-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ba0fe-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ba0fe-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ba0fe-113">Peut</span><span class="sxs-lookup"><span data-stu-id="ba0fe-113">'T</span></span>

<span data-ttu-id="ba0fe-114">Cible sur laquelle les opérations du tableau agissent.</span><span class="sxs-lookup"><span data-stu-id="ba0fe-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba0fe-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba0fe-115">See Also</span></span>

- [<span data-ttu-id="ba0fe-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="ba0fe-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)