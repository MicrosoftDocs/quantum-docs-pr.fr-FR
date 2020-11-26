---
uid: Microsoft.Quantum.Canon.BoundA
title: Fonction liée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216946"
---
# <a name="bounda-function"></a><span data-ttu-id="4e084-102">Fonction liée</span><span class="sxs-lookup"><span data-stu-id="4e084-102">BoundA function</span></span>

<span data-ttu-id="4e084-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4e084-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4e084-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e084-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e084-105">À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="4e084-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="4e084-106">Le modificateur `A` indique que toutes les opérations dans le tableau sont adjointable.</span><span class="sxs-lookup"><span data-stu-id="4e084-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="4e084-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="4e084-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="4e084-108">opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est ADJ []</span><span class="sxs-lookup"><span data-stu-id="4e084-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="4e084-109">Séquence d’opérations à effectuer sur une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="4e084-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="4e084-110">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="4e084-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="4e084-111">Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.</span><span class="sxs-lookup"><span data-stu-id="4e084-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4e084-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4e084-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e084-113">Peut</span><span class="sxs-lookup"><span data-stu-id="4e084-113">'T</span></span>

<span data-ttu-id="4e084-114">Cible sur laquelle les opérations du tableau agissent.</span><span class="sxs-lookup"><span data-stu-id="4e084-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e084-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e084-115">See Also</span></span>

- [<span data-ttu-id="4e084-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="4e084-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)