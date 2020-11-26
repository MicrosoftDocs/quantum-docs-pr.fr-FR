---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: Opération ApplyIfZero
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3b14ef8a1aa736fe096a21fe51be5a7c5bb1d09d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209431"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="cc860-102">Opération ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="cc860-102">ApplyIfZero operation</span></span>

<span data-ttu-id="cc860-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cc860-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cc860-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc860-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc860-105">Applique une opération conditionnée sur une valeur de résultat classique égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="cc860-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="cc860-106">Description</span><span class="sxs-lookup"><span data-stu-id="cc860-106">Description</span></span>

<span data-ttu-id="cc860-107">Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `Zero` .</span><span class="sxs-lookup"><span data-stu-id="cc860-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="cc860-108">Si `One` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="cc860-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="cc860-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="cc860-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="cc860-110">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="cc860-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="cc860-111">Résultat de mesure qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="cc860-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="cc860-112">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc860-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cc860-113">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="cc860-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="cc860-114">cible : 't</span><span class="sxs-lookup"><span data-stu-id="cc860-114">target : 'T</span></span>

<span data-ttu-id="cc860-115">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="cc860-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc860-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc860-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cc860-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="cc860-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cc860-118">Peut</span><span class="sxs-lookup"><span data-stu-id="cc860-118">'T</span></span>

<span data-ttu-id="cc860-119">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="cc860-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc860-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc860-120">See Also</span></span>

- [<span data-ttu-id="cc860-121">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="cc860-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="cc860-122">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="cc860-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="cc860-123">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="cc860-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)