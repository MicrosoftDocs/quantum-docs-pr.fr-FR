---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Opération ApplyToFirstQubitC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2659c3a97baa68cb4c1d7781381f89742902594d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217507"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="78b9c-102">Opération ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="78b9c-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="78b9c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="78b9c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="78b9c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78b9c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78b9c-105">Applique l’opération op au premier qubit du Registre.</span><span class="sxs-lookup"><span data-stu-id="78b9c-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="78b9c-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="78b9c-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="78b9c-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="78b9c-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="78b9c-108">OP : [Qubit](xref:microsoft.quantum.lang-ref.qubit) l' => [unité](xref:microsoft.quantum.lang-ref.unit) qubit est CTL</span><span class="sxs-lookup"><span data-stu-id="78b9c-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="78b9c-109">Opération à appliquer au premier qubit</span><span class="sxs-lookup"><span data-stu-id="78b9c-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="78b9c-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="78b9c-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="78b9c-111">Tableau qubit vers le premier qubit auquel l’opération est appliquée</span><span class="sxs-lookup"><span data-stu-id="78b9c-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="78b9c-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78b9c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="78b9c-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="78b9c-113">See Also</span></span>

- [<span data-ttu-id="78b9c-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="78b9c-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)