---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: Opération ApplyToElement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5c321d95c9b79bc50827c2b50c406b164e143dc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704934"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="47998-102">Opération ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="47998-102">ApplyToElement operation</span></span>

<span data-ttu-id="47998-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="47998-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="47998-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47998-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47998-105">Applique une opération à un élément donné d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="47998-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="47998-106">Description</span><span class="sxs-lookup"><span data-stu-id="47998-106">Description</span></span>

<span data-ttu-id="47998-107">À partir d’une opération `op` , d’un index `index` et d’un tableau de cibles `targets` , s’applique `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="47998-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="47998-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="47998-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="47998-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47998-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="47998-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="47998-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="47998-111">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47998-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47998-112">Index dans le tableau de cibles.</span><span class="sxs-lookup"><span data-stu-id="47998-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="47998-113">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="47998-113">targets : 'T[]</span></span>

<span data-ttu-id="47998-114">Tableau de cibles possibles pour `op` .</span><span class="sxs-lookup"><span data-stu-id="47998-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47998-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47998-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="47998-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="47998-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47998-117">Peut</span><span class="sxs-lookup"><span data-stu-id="47998-117">'T</span></span>

<span data-ttu-id="47998-118">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="47998-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="47998-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47998-119">See Also</span></span>

- [<span data-ttu-id="47998-120">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="47998-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="47998-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="47998-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="47998-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="47998-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)