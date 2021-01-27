---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Opération ApplyIf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841868"
---
# <a name="applyif-operation"></a><span data-ttu-id="ee1c9-102">Opération ApplyIf</span><span class="sxs-lookup"><span data-stu-id="ee1c9-102">ApplyIf operation</span></span>

<span data-ttu-id="ee1c9-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ee1c9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ee1c9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee1c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee1c9-105">Applique une opération conditionnée sur un bit classique.</span><span class="sxs-lookup"><span data-stu-id="ee1c9-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="ee1c9-106">Description</span><span class="sxs-lookup"><span data-stu-id="ee1c9-106">Description</span></span>

<span data-ttu-id="ee1c9-107">Pour une opération donnée `op` et une valeur de bit `bit` , s’applique `op` à `target` si `bit` est `true` .</span><span class="sxs-lookup"><span data-stu-id="ee1c9-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="ee1c9-108">Si `false` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="ee1c9-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="ee1c9-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="ee1c9-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ee1c9-110">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee1c9-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ee1c9-111">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="ee1c9-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="ee1c9-112">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ee1c9-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ee1c9-113">valeur booléenne qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="ee1c9-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="ee1c9-114">cible : 't</span><span class="sxs-lookup"><span data-stu-id="ee1c9-114">target : 'T</span></span>

<span data-ttu-id="ee1c9-115">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="ee1c9-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee1c9-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee1c9-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ee1c9-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ee1c9-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee1c9-118">Peut</span><span class="sxs-lookup"><span data-stu-id="ee1c9-118">'T</span></span>

<span data-ttu-id="ee1c9-119">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="ee1c9-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="ee1c9-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="ee1c9-120">Example</span></span>

<span data-ttu-id="ee1c9-121">L’exemple suivant prépare un registre de qubits dans un état de base de calcul représenté par une chaîne de bits classique donnée sous la forme d’un tableau de `Bool` valeurs :</span><span class="sxs-lookup"><span data-stu-id="ee1c9-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="ee1c9-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee1c9-122">See Also</span></span>

- [<span data-ttu-id="ee1c9-123">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="ee1c9-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="ee1c9-124">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="ee1c9-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="ee1c9-125">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="ee1c9-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)