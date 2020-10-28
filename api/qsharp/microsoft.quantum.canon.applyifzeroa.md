---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Opération ApplyIfZeroA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: d324cd970e8df49ceb51b6bf5c9f3c9c3ff142f9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705246"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="e09c7-102">Opération ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="e09c7-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="e09c7-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e09c7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e09c7-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e09c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e09c7-105">Applique une opération adjointable conditionnée sur une valeur de résultat classique égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="e09c7-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="e09c7-106">Description</span><span class="sxs-lookup"><span data-stu-id="e09c7-106">Description</span></span>

<span data-ttu-id="e09c7-107">Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `Zero` .</span><span class="sxs-lookup"><span data-stu-id="e09c7-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="e09c7-108">Si `One` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="e09c7-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="e09c7-109">Le suffixe `A` indique que l’opération à appliquer est adjointable.</span><span class="sxs-lookup"><span data-stu-id="e09c7-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="e09c7-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="e09c7-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="e09c7-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="e09c7-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="e09c7-112">Résultat de mesure qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="e09c7-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="e09c7-113">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e09c7-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e09c7-114">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="e09c7-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="e09c7-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="e09c7-115">target : 'T</span></span>

<span data-ttu-id="e09c7-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="e09c7-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e09c7-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e09c7-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e09c7-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e09c7-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e09c7-119">Peut</span><span class="sxs-lookup"><span data-stu-id="e09c7-119">'T</span></span>

<span data-ttu-id="e09c7-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="e09c7-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e09c7-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e09c7-121">See Also</span></span>

- [<span data-ttu-id="e09c7-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="e09c7-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="e09c7-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="e09c7-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="e09c7-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="e09c7-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)