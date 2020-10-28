---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704435"
---
# <a name="boundca-function"></a><span data-ttu-id="c60f6-102">BoundCA fonction)</span><span class="sxs-lookup"><span data-stu-id="c60f6-102">BoundCA function</span></span>

<span data-ttu-id="c60f6-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c60f6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c60f6-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c60f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c60f6-105">À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="c60f6-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="c60f6-106">Le modificateur `CA` indique que toutes les opérations dans le tableau sont adjointable et contrôlable.</span><span class="sxs-lookup"><span data-stu-id="c60f6-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c60f6-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="c60f6-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="c60f6-108">opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="c60f6-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="c60f6-109">Séquence d’opérations à effectuer sur une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="c60f6-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="c60f6-110">Sortie : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="c60f6-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c60f6-111">Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.</span><span class="sxs-lookup"><span data-stu-id="c60f6-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c60f6-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c60f6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c60f6-113">Peut</span><span class="sxs-lookup"><span data-stu-id="c60f6-113">'T</span></span>

<span data-ttu-id="c60f6-114">Cible sur laquelle les opérations du tableau agissent.</span><span class="sxs-lookup"><span data-stu-id="c60f6-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="c60f6-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c60f6-115">See Also</span></span>

- [<span data-ttu-id="c60f6-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="c60f6-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)