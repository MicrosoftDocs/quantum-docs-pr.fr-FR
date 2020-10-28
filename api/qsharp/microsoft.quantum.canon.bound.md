---
uid: Microsoft.Quantum.Canon.Bound
title: Fonction Bound
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704475"
---
# <a name="bound-function"></a><span data-ttu-id="9ec74-102">Fonction Bound</span><span class="sxs-lookup"><span data-stu-id="9ec74-102">Bound function</span></span>

<span data-ttu-id="9ec74-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ec74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ec74-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ec74-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ec74-105">À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="9ec74-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="9ec74-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9ec74-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="9ec74-107">opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="9ec74-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="9ec74-108">Séquence d’opérations à effectuer sur une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="9ec74-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="9ec74-109">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ec74-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9ec74-110">Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.</span><span class="sxs-lookup"><span data-stu-id="9ec74-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9ec74-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9ec74-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ec74-112">Peut</span><span class="sxs-lookup"><span data-stu-id="9ec74-112">'T</span></span>

<span data-ttu-id="9ec74-113">Cible sur laquelle les opérations du tableau agissent.</span><span class="sxs-lookup"><span data-stu-id="9ec74-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ec74-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ec74-114">See Also</span></span>

- [<span data-ttu-id="9ec74-115">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="9ec74-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="9ec74-116">Microsoft. Quantum. Canon. bounda</span><span class="sxs-lookup"><span data-stu-id="9ec74-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="9ec74-117">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="9ec74-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)