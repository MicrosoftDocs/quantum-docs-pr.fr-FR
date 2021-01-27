---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: Opération ApplyIfZero
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 215b71a8d2e4f8a22df05b210824bc40a969b6f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841747"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="110d3-102">Opération ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="110d3-102">ApplyIfZero operation</span></span>

<span data-ttu-id="110d3-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="110d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="110d3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="110d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="110d3-105">Applique une opération conditionnée sur une valeur de résultat classique égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="110d3-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="110d3-106">Description</span><span class="sxs-lookup"><span data-stu-id="110d3-106">Description</span></span>

<span data-ttu-id="110d3-107">Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `Zero` .</span><span class="sxs-lookup"><span data-stu-id="110d3-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="110d3-108">Si `One` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="110d3-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="110d3-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="110d3-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="110d3-110">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="110d3-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="110d3-111">Résultat de mesure qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="110d3-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="110d3-112">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="110d3-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="110d3-113">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="110d3-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="110d3-114">cible : 't</span><span class="sxs-lookup"><span data-stu-id="110d3-114">target : 'T</span></span>

<span data-ttu-id="110d3-115">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="110d3-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="110d3-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="110d3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="110d3-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="110d3-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="110d3-118">Peut</span><span class="sxs-lookup"><span data-stu-id="110d3-118">'T</span></span>

<span data-ttu-id="110d3-119">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="110d3-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="110d3-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="110d3-120">See Also</span></span>

- [<span data-ttu-id="110d3-121">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="110d3-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="110d3-122">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="110d3-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="110d3-123">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="110d3-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)