---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Opération ApplyIf
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c5a1012328fa012ee02707aa59c94ac9c44b8e87
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218833"
---
# <a name="applyif-operation"></a><span data-ttu-id="37257-102">Opération ApplyIf</span><span class="sxs-lookup"><span data-stu-id="37257-102">ApplyIf operation</span></span>

<span data-ttu-id="37257-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="37257-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="37257-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37257-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37257-105">Applique une opération conditionnée sur un bit classique.</span><span class="sxs-lookup"><span data-stu-id="37257-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="37257-106">Description</span><span class="sxs-lookup"><span data-stu-id="37257-106">Description</span></span>

<span data-ttu-id="37257-107">Pour une opération donnée `op` et une valeur de bit `bit` , s’applique `op` à `target` si `bit` est `true` .</span><span class="sxs-lookup"><span data-stu-id="37257-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="37257-108">Si `false` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="37257-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="37257-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="37257-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="37257-110">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37257-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="37257-111">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="37257-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="37257-112">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="37257-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="37257-113">valeur booléenne qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="37257-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="37257-114">cible : 't</span><span class="sxs-lookup"><span data-stu-id="37257-114">target : 'T</span></span>

<span data-ttu-id="37257-115">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="37257-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37257-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37257-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="37257-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="37257-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37257-118">Peut</span><span class="sxs-lookup"><span data-stu-id="37257-118">'T</span></span>

<span data-ttu-id="37257-119">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="37257-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="37257-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="37257-120">See Also</span></span>

- [<span data-ttu-id="37257-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="37257-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="37257-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="37257-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="37257-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="37257-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)