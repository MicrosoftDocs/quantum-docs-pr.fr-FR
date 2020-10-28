---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704406"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="263f8-102">CControlledA fonction)</span><span class="sxs-lookup"><span data-stu-id="263f8-102">CControlledA function</span></span>

<span data-ttu-id="263f8-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="263f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="263f8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="263f8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="263f8-105">Dans le cas d’une opération op, retourne une nouvelle opération qui applique le op si un bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="263f8-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="263f8-106">Si la `false` valeur est, rien ne se produit.</span><span class="sxs-lookup"><span data-stu-id="263f8-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="263f8-107">Le modificateur `A` indique que l’opération est adjointable.</span><span class="sxs-lookup"><span data-stu-id="263f8-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="263f8-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="263f8-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="263f8-109">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="263f8-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="263f8-110">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="263f8-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="263f8-111">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="263f8-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="263f8-112">Nouvelle opération qui est op si le bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="263f8-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="263f8-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="263f8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="263f8-114">Peut</span><span class="sxs-lookup"><span data-stu-id="263f8-114">'T</span></span>

<span data-ttu-id="263f8-115">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="263f8-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="263f8-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="263f8-116">See Also</span></span>

- [<span data-ttu-id="263f8-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="263f8-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)