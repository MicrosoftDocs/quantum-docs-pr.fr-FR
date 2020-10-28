---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Opération ApplyIfA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 279a069176ee24ed83406f72170462bf58c790d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705363"
---
# <a name="applyifa-operation"></a><span data-ttu-id="7c8da-102">Opération ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="7c8da-102">ApplyIfA operation</span></span>

<span data-ttu-id="7c8da-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7c8da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7c8da-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c8da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c8da-105">Applique une opération adjointable conditionnée sur un bit classique.</span><span class="sxs-lookup"><span data-stu-id="7c8da-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="7c8da-106">Description</span><span class="sxs-lookup"><span data-stu-id="7c8da-106">Description</span></span>

<span data-ttu-id="7c8da-107">Pour une opération donnée `op` et une valeur de bit `bit` , s’applique `op` à `target` si `bit` est `true` .</span><span class="sxs-lookup"><span data-stu-id="7c8da-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="7c8da-108">Si `false` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="7c8da-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="7c8da-109">Le suffixe `A` indique que l’opération à appliquer est adjointable.</span><span class="sxs-lookup"><span data-stu-id="7c8da-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="7c8da-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="7c8da-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="7c8da-111">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c8da-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7c8da-112">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="7c8da-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="7c8da-113">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7c8da-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7c8da-114">valeur booléenne qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="7c8da-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="7c8da-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="7c8da-115">target : 'T</span></span>

<span data-ttu-id="7c8da-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="7c8da-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c8da-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c8da-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7c8da-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7c8da-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7c8da-119">Peut</span><span class="sxs-lookup"><span data-stu-id="7c8da-119">'T</span></span>

<span data-ttu-id="7c8da-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="7c8da-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c8da-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c8da-121">See Also</span></span>

- [<span data-ttu-id="7c8da-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="7c8da-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="7c8da-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="7c8da-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="7c8da-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="7c8da-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)