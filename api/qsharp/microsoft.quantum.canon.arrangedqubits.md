---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704499"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="85529-102">ArrangedQubits fonction)</span><span class="sxs-lookup"><span data-stu-id="85529-102">ArrangedQubits function</span></span>

<span data-ttu-id="85529-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="85529-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="85529-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="85529-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="85529-105">Organiser le contrôle, la cible et les qubits d’assistance en fonction d’un index</span><span class="sxs-lookup"><span data-stu-id="85529-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="85529-106">Description</span><span class="sxs-lookup"><span data-stu-id="85529-106">Description</span></span>

<span data-ttu-id="85529-107">Retourne un tableau qubit avec la cible à l’index 0 et le contrôle i à l’index 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="85529-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="85529-108">Les qubits d’assistance sont insérés à toutes les autres positions dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="85529-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="85529-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="85529-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="85529-110">contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="85529-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="85529-111">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="85529-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="85529-112">Helper : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="85529-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="85529-113">Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="85529-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

