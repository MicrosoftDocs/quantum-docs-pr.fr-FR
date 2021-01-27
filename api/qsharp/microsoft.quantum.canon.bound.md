---
uid: Microsoft.Quantum.Canon.Bound
title: Fonction Bound
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841066"
---
# <a name="bound-function"></a><span data-ttu-id="0ce98-102">Fonction Bound</span><span class="sxs-lookup"><span data-stu-id="0ce98-102">Bound function</span></span>

<span data-ttu-id="0ce98-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0ce98-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0ce98-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0ce98-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0ce98-105">À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="0ce98-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="0ce98-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0ce98-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="0ce98-107">opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="0ce98-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="0ce98-108">Séquence d’opérations à effectuer sur une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="0ce98-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="0ce98-109">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0ce98-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0ce98-110">Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.</span><span class="sxs-lookup"><span data-stu-id="0ce98-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0ce98-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0ce98-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0ce98-112">Peut</span><span class="sxs-lookup"><span data-stu-id="0ce98-112">'T</span></span>

<span data-ttu-id="0ce98-113">Cible sur laquelle les opérations du tableau agissent.</span><span class="sxs-lookup"><span data-stu-id="0ce98-113">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="0ce98-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="0ce98-114">Example</span></span>

<span data-ttu-id="0ce98-115">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="0ce98-115">The following are equivalent:</span></span>

```qsharp
let bound = Bound([U, V]);
bound(x);
```

<span data-ttu-id="0ce98-116">and</span><span class="sxs-lookup"><span data-stu-id="0ce98-116">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="0ce98-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ce98-117">See Also</span></span>

- [<span data-ttu-id="0ce98-118">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="0ce98-118">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="0ce98-119">Microsoft. Quantum. Canon. bounda</span><span class="sxs-lookup"><span data-stu-id="0ce98-119">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="0ce98-120">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="0ce98-120">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)