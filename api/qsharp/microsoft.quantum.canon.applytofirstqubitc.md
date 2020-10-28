---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Opération ApplyToFirstQubitC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704878"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="39d87-102">Opération ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="39d87-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="39d87-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39d87-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39d87-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39d87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39d87-105">Applique l’opération op au premier qubit du Registre.</span><span class="sxs-lookup"><span data-stu-id="39d87-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="39d87-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="39d87-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="39d87-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="39d87-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="39d87-108">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit) d' => [unités](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="39d87-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="39d87-109">Opération à appliquer au premier qubit</span><span class="sxs-lookup"><span data-stu-id="39d87-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="39d87-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="39d87-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="39d87-111">Tableau qubit vers le premier qubit auquel l’opération est appliquée</span><span class="sxs-lookup"><span data-stu-id="39d87-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="39d87-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39d87-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="39d87-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39d87-113">See Also</span></span>

- [<span data-ttu-id="39d87-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="39d87-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)