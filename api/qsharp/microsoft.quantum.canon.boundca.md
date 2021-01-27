---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844527"
---
# <a name="boundca-function"></a><span data-ttu-id="350f1-102">BoundCA fonction)</span><span class="sxs-lookup"><span data-stu-id="350f1-102">BoundCA function</span></span>

<span data-ttu-id="350f1-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="350f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="350f1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="350f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="350f1-105">À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="350f1-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="350f1-106">Le modificateur `CA` indique que toutes les opérations dans le tableau sont adjointable et contrôlable.</span><span class="sxs-lookup"><span data-stu-id="350f1-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="350f1-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="350f1-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="350f1-108">opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="350f1-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="350f1-109">Séquence d’opérations à effectuer sur une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="350f1-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="350f1-110">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="350f1-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="350f1-111">Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.</span><span class="sxs-lookup"><span data-stu-id="350f1-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="350f1-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="350f1-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="350f1-113">Peut</span><span class="sxs-lookup"><span data-stu-id="350f1-113">'T</span></span>

<span data-ttu-id="350f1-114">Cible sur laquelle les opérations du tableau agissent.</span><span class="sxs-lookup"><span data-stu-id="350f1-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="350f1-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="350f1-115">Example</span></span>

<span data-ttu-id="350f1-116">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="350f1-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="350f1-117">and</span><span class="sxs-lookup"><span data-stu-id="350f1-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="350f1-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="350f1-118">See Also</span></span>

- [<span data-ttu-id="350f1-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="350f1-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)