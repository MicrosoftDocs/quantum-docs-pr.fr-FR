---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: Opération ApplyIfZeroCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 85612bd3dd7af45b7901fef775a7d556eb229608
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705219"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="20ed8-102">Opération ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="20ed8-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="20ed8-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20ed8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20ed8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20ed8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20ed8-105">Applique une opération unitaire conditionnée sur une valeur de résultat classique égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="20ed8-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="20ed8-106">Description</span><span class="sxs-lookup"><span data-stu-id="20ed8-106">Description</span></span>

<span data-ttu-id="20ed8-107">Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `Zero` .</span><span class="sxs-lookup"><span data-stu-id="20ed8-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="20ed8-108">Si `One` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="20ed8-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="20ed8-109">Le suffixe `CA` indique que l’opération à appliquer est unitaire (contrôlable et adjointable).</span><span class="sxs-lookup"><span data-stu-id="20ed8-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="20ed8-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="20ed8-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="20ed8-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="20ed8-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="20ed8-112">Résultat de mesure qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="20ed8-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="20ed8-113">OP : t [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="20ed8-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="20ed8-114">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="20ed8-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="20ed8-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="20ed8-115">target : 'T</span></span>

<span data-ttu-id="20ed8-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="20ed8-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20ed8-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20ed8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="20ed8-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="20ed8-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20ed8-119">Peut</span><span class="sxs-lookup"><span data-stu-id="20ed8-119">'T</span></span>

<span data-ttu-id="20ed8-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="20ed8-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="20ed8-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20ed8-121">See Also</span></span>

- [<span data-ttu-id="20ed8-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="20ed8-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="20ed8-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="20ed8-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="20ed8-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="20ed8-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)