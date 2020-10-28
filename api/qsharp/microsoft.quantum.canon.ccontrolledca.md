---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704398"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="07e8e-102">CControlledCA fonction)</span><span class="sxs-lookup"><span data-stu-id="07e8e-102">CControlledCA function</span></span>

<span data-ttu-id="07e8e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="07e8e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="07e8e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07e8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07e8e-105">Dans le cas d’une opération op, retourne une nouvelle opération qui applique le op si un bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="07e8e-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="07e8e-106">Si la `false` valeur est, rien ne se produit.</span><span class="sxs-lookup"><span data-stu-id="07e8e-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="07e8e-107">Le modificateur `CA` indique que l’opération est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="07e8e-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="07e8e-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="07e8e-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="07e8e-109">OP : 't => d' [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="07e8e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="07e8e-110">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="07e8e-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="07e8e-111">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't) = [> liste](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="07e8e-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="07e8e-112">Nouvelle opération qui est op si le bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="07e8e-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="07e8e-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="07e8e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="07e8e-114">Peut</span><span class="sxs-lookup"><span data-stu-id="07e8e-114">'T</span></span>

<span data-ttu-id="07e8e-115">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="07e8e-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="07e8e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07e8e-116">See Also</span></span>

- [<span data-ttu-id="07e8e-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="07e8e-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)