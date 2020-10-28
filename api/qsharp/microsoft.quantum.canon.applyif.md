---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Opération ApplyIf
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705358"
---
# <a name="applyif-operation"></a><span data-ttu-id="d7982-102">Opération ApplyIf</span><span class="sxs-lookup"><span data-stu-id="d7982-102">ApplyIf operation</span></span>

<span data-ttu-id="d7982-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d7982-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d7982-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7982-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7982-105">Applique une opération conditionnée sur un bit classique.</span><span class="sxs-lookup"><span data-stu-id="d7982-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="d7982-106">Description</span><span class="sxs-lookup"><span data-stu-id="d7982-106">Description</span></span>

<span data-ttu-id="d7982-107">Pour une opération donnée `op` et une valeur de bit `bit` , s’applique `op` à `target` si `bit` est `true` .</span><span class="sxs-lookup"><span data-stu-id="d7982-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="d7982-108">Si `false` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="d7982-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="d7982-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="d7982-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="d7982-110">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7982-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d7982-111">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="d7982-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="d7982-112">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d7982-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d7982-113">valeur booléenne qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="d7982-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="d7982-114">cible : 't</span><span class="sxs-lookup"><span data-stu-id="d7982-114">target : 'T</span></span>

<span data-ttu-id="d7982-115">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="d7982-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7982-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7982-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d7982-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d7982-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7982-118">Peut</span><span class="sxs-lookup"><span data-stu-id="d7982-118">'T</span></span>

<span data-ttu-id="d7982-119">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="d7982-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7982-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7982-120">See Also</span></span>

- [<span data-ttu-id="d7982-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="d7982-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="d7982-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="d7982-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="d7982-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="d7982-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)