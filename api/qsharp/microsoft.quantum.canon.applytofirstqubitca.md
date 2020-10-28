---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Opération ApplyToFirstQubitCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704870"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="237bd-102">Opération ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="237bd-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="237bd-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="237bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="237bd-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="237bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="237bd-105">Applique l’opération op au premier qubit du Registre.</span><span class="sxs-lookup"><span data-stu-id="237bd-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="237bd-106">Le modificateur `CA` indique que l’opération est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="237bd-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="237bd-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="237bd-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="237bd-108">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit) d' => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="237bd-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="237bd-109">Opération à appliquer au premier qubit</span><span class="sxs-lookup"><span data-stu-id="237bd-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="237bd-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="237bd-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="237bd-111">Tableau qubit vers le premier qubit auquel l’opération est appliquée</span><span class="sxs-lookup"><span data-stu-id="237bd-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="237bd-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="237bd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="237bd-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="237bd-113">See Also</span></span>

- [<span data-ttu-id="237bd-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="237bd-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)