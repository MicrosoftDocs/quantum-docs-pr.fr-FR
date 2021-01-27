---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Opération ApplyToRestA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841261"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="b0da4-102">Opération ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="b0da4-102">ApplyToRestA operation</span></span>

<span data-ttu-id="b0da4-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b0da4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b0da4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0da4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0da4-105">Applique une opération à tous les éléments à l’exception du premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="b0da4-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="b0da4-106">Description</span><span class="sxs-lookup"><span data-stu-id="b0da4-106">Description</span></span>

<span data-ttu-id="b0da4-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b0da4-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b0da4-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="b0da4-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="b0da4-109">OP : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="b0da4-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b0da4-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="b0da4-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b0da4-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="b0da4-111">targets : 'T[]</span></span>

<span data-ttu-id="b0da4-112">Tableau de cibles, dont tous les sauf le premier seront appliqués `op` .</span><span class="sxs-lookup"><span data-stu-id="b0da4-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0da4-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0da4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b0da4-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b0da4-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b0da4-115">Peut</span><span class="sxs-lookup"><span data-stu-id="b0da4-115">'T</span></span>

<span data-ttu-id="b0da4-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="b0da4-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0da4-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0da4-117">See Also</span></span>

- [<span data-ttu-id="b0da4-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="b0da4-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="b0da4-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="b0da4-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="b0da4-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="b0da4-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)