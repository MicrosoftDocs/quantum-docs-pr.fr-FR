---
uid: Microsoft.Quantum.Canon.BoundA
title: Fonction liée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704467"
---
# <a name="bounda-function"></a><span data-ttu-id="fc290-102">Fonction liée</span><span class="sxs-lookup"><span data-stu-id="fc290-102">BoundA function</span></span>

<span data-ttu-id="fc290-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fc290-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fc290-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc290-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc290-105">À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="fc290-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="fc290-106">Le modificateur `A` indique que toutes les opérations dans le tableau sont adjointable.</span><span class="sxs-lookup"><span data-stu-id="fc290-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="fc290-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="fc290-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="fc290-108">opérations : 't => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="fc290-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="fc290-109">Séquence d’opérations à effectuer sur une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="fc290-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="fc290-110">Sortie : 't => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc290-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fc290-111">Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.</span><span class="sxs-lookup"><span data-stu-id="fc290-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fc290-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="fc290-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc290-113">Peut</span><span class="sxs-lookup"><span data-stu-id="fc290-113">'T</span></span>

<span data-ttu-id="fc290-114">Cible sur laquelle les opérations du tableau agissent.</span><span class="sxs-lookup"><span data-stu-id="fc290-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc290-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc290-115">See Also</span></span>

- [<span data-ttu-id="fc290-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="fc290-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)