---
uid: Microsoft.Quantum.Canon.BoundA
title: Fonction liée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844541"
---
# <a name="bounda-function"></a><span data-ttu-id="48c98-102">Fonction liée</span><span class="sxs-lookup"><span data-stu-id="48c98-102">BoundA function</span></span>

<span data-ttu-id="48c98-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="48c98-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="48c98-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48c98-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48c98-105">À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="48c98-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="48c98-106">Le modificateur `A` indique que toutes les opérations dans le tableau sont adjointable.</span><span class="sxs-lookup"><span data-stu-id="48c98-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="48c98-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="48c98-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="48c98-108">opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est ADJ []</span><span class="sxs-lookup"><span data-stu-id="48c98-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="48c98-109">Séquence d’opérations à effectuer sur une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="48c98-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="48c98-110">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="48c98-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="48c98-111">Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.</span><span class="sxs-lookup"><span data-stu-id="48c98-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="48c98-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="48c98-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48c98-113">Peut</span><span class="sxs-lookup"><span data-stu-id="48c98-113">'T</span></span>

<span data-ttu-id="48c98-114">Cible sur laquelle les opérations du tableau agissent.</span><span class="sxs-lookup"><span data-stu-id="48c98-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="48c98-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="48c98-115">Example</span></span>

<span data-ttu-id="48c98-116">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="48c98-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

<span data-ttu-id="48c98-117">and</span><span class="sxs-lookup"><span data-stu-id="48c98-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="48c98-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48c98-118">See Also</span></span>

- [<span data-ttu-id="48c98-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="48c98-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)