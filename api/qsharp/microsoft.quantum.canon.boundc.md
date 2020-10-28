---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704454"
---
# <a name="boundc-function"></a><span data-ttu-id="4946e-102">BoundC fonction)</span><span class="sxs-lookup"><span data-stu-id="4946e-102">BoundC function</span></span>

<span data-ttu-id="4946e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4946e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4946e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4946e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4946e-105">À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="4946e-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="4946e-106">Le modificateur `C` indique que toutes les opérations dans le tableau sont contrôlables.</span><span class="sxs-lookup"><span data-stu-id="4946e-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="4946e-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="4946e-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="4946e-108">opérations : 't => CTL d' [unité](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="4946e-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="4946e-109">Séquence d’opérations à effectuer sur une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="4946e-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="4946e-110">Sortie : 't => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4946e-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="4946e-111">Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.</span><span class="sxs-lookup"><span data-stu-id="4946e-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4946e-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4946e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4946e-113">Peut</span><span class="sxs-lookup"><span data-stu-id="4946e-113">'T</span></span>

<span data-ttu-id="4946e-114">Cible sur laquelle les opérations du tableau agissent.</span><span class="sxs-lookup"><span data-stu-id="4946e-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="4946e-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4946e-115">See Also</span></span>

- [<span data-ttu-id="4946e-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="4946e-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)