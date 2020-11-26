---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Opération ApplyIfA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218765"
---
# <a name="applyifa-operation"></a><span data-ttu-id="cfaa6-102">Opération ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="cfaa6-102">ApplyIfA operation</span></span>

<span data-ttu-id="cfaa6-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cfaa6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cfaa6-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfaa6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfaa6-105">Applique une opération adjointable conditionnée sur un bit classique.</span><span class="sxs-lookup"><span data-stu-id="cfaa6-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="cfaa6-106">Description</span><span class="sxs-lookup"><span data-stu-id="cfaa6-106">Description</span></span>

<span data-ttu-id="cfaa6-107">Pour une opération donnée `op` et une valeur de bit `bit` , s’applique `op` à `target` si `bit` est `true` .</span><span class="sxs-lookup"><span data-stu-id="cfaa6-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="cfaa6-108">Si `false` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="cfaa6-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="cfaa6-109">Le suffixe `A` indique que l’opération à appliquer est adjointable.</span><span class="sxs-lookup"><span data-stu-id="cfaa6-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="cfaa6-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="cfaa6-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="cfaa6-111">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="cfaa6-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="cfaa6-112">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="cfaa6-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="cfaa6-113">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cfaa6-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cfaa6-114">valeur booléenne qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="cfaa6-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="cfaa6-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="cfaa6-115">target : 'T</span></span>

<span data-ttu-id="cfaa6-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="cfaa6-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cfaa6-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfaa6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cfaa6-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="cfaa6-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cfaa6-119">Peut</span><span class="sxs-lookup"><span data-stu-id="cfaa6-119">'T</span></span>

<span data-ttu-id="cfaa6-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="cfaa6-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfaa6-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cfaa6-121">See Also</span></span>

- [<span data-ttu-id="cfaa6-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="cfaa6-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="cfaa6-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="cfaa6-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="cfaa6-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="cfaa6-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)