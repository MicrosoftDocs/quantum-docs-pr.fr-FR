---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Opération ApplyToFirstQubitA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704875"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="aa4e2-102">Opération ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="aa4e2-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="aa4e2-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa4e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa4e2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa4e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa4e2-105">Applique une opération au premier qubit dans le registre.</span><span class="sxs-lookup"><span data-stu-id="aa4e2-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="aa4e2-106">Le modificateur `A` indique que l’opération est adjointable.</span><span class="sxs-lookup"><span data-stu-id="aa4e2-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="aa4e2-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="aa4e2-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="aa4e2-108">opération : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) qubit</span><span class="sxs-lookup"><span data-stu-id="aa4e2-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aa4e2-109">Opération à appliquer au premier qubit</span><span class="sxs-lookup"><span data-stu-id="aa4e2-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="aa4e2-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aa4e2-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aa4e2-111">Tableau qubit vers le premier qubit auquel l’opération est appliquée</span><span class="sxs-lookup"><span data-stu-id="aa4e2-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa4e2-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa4e2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="aa4e2-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aa4e2-113">See Also</span></span>

- [<span data-ttu-id="aa4e2-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="aa4e2-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)