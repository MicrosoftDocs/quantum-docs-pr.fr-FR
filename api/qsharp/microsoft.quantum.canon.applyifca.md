---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Opération ApplyIfCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b0ac469d6dea51951e0d9b2cfceb54253d4b4c5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209619"
---
# <a name="applyifca-operation"></a><span data-ttu-id="34792-102">Opération ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="34792-102">ApplyIfCA operation</span></span>

<span data-ttu-id="34792-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="34792-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="34792-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34792-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34792-105">Applique une opération unitaire conditionnée sur un bit classique.</span><span class="sxs-lookup"><span data-stu-id="34792-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="34792-106">Description</span><span class="sxs-lookup"><span data-stu-id="34792-106">Description</span></span>

<span data-ttu-id="34792-107">Pour une opération donnée `op` et une valeur de bit `bit` , s’applique `op` à `target` si `bit` est `true` .</span><span class="sxs-lookup"><span data-stu-id="34792-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="34792-108">Si `false` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="34792-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="34792-109">Le suffixe `CA` indique que l’opération à appliquer est unitaire (contrôlable et adjointable).</span><span class="sxs-lookup"><span data-stu-id="34792-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="34792-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="34792-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="34792-111">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="34792-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="34792-112">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="34792-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="34792-113">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="34792-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="34792-114">valeur booléenne qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="34792-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="34792-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="34792-115">target : 'T</span></span>

<span data-ttu-id="34792-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="34792-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="34792-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34792-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="34792-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="34792-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="34792-119">Peut</span><span class="sxs-lookup"><span data-stu-id="34792-119">'T</span></span>

<span data-ttu-id="34792-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="34792-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="34792-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34792-121">See Also</span></span>

- [<span data-ttu-id="34792-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="34792-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="34792-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="34792-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="34792-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="34792-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)