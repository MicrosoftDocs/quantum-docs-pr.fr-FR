---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: Opération ApplyIfOne
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: 8c668423d126f02736bcb541e73e210a761c5719
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705275"
---
# <a name="applyifone-operation"></a><span data-ttu-id="786ef-102">Opération ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="786ef-102">ApplyIfOne operation</span></span>

<span data-ttu-id="786ef-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="786ef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="786ef-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="786ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="786ef-105">Applique une opération conditionnée sur une valeur de résultat classique qui en est une.</span><span class="sxs-lookup"><span data-stu-id="786ef-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="786ef-106">Description</span><span class="sxs-lookup"><span data-stu-id="786ef-106">Description</span></span>

<span data-ttu-id="786ef-107">Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `One` .</span><span class="sxs-lookup"><span data-stu-id="786ef-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="786ef-108">Si `Zero` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="786ef-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="786ef-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="786ef-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="786ef-110">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="786ef-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="786ef-111">Résultat de mesure qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="786ef-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="786ef-112">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="786ef-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="786ef-113">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="786ef-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="786ef-114">cible : 't</span><span class="sxs-lookup"><span data-stu-id="786ef-114">target : 'T</span></span>

<span data-ttu-id="786ef-115">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="786ef-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="786ef-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="786ef-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="786ef-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="786ef-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="786ef-118">Peut</span><span class="sxs-lookup"><span data-stu-id="786ef-118">'T</span></span>

<span data-ttu-id="786ef-119">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="786ef-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="786ef-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="786ef-120">See Also</span></span>

- [<span data-ttu-id="786ef-121">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="786ef-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="786ef-122">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="786ef-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="786ef-123">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="786ef-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)