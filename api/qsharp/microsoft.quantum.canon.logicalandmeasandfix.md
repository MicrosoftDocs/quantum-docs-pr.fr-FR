---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Opération LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704030"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="86034-102">Opération LogicalANDMeasAndFix</span><span class="sxs-lookup"><span data-stu-id="86034-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="86034-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="86034-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="86034-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86034-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86034-105">Calcule le AND logique de plusieurs qubits.</span><span class="sxs-lookup"><span data-stu-id="86034-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="86034-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="86034-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="86034-107">ctrlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="86034-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="86034-108">Entrée qubits dans l’entrée multiple et la porte.</span><span class="sxs-lookup"><span data-stu-id="86034-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="86034-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="86034-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="86034-110">Qubit sur lequel est écrit la sortie de et.</span><span class="sxs-lookup"><span data-stu-id="86034-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="86034-111">Cela est supposé démarrer toujours dans l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="86034-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86034-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86034-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="86034-113">Notes</span><span class="sxs-lookup"><span data-stu-id="86034-113">Remarks</span></span>

<span data-ttu-id="86034-114">Quand `ctrlRegister` a exactement $2 $ qubits, cela équivaut à l’opération mais à la phase `CCNOT` avec une phase $e ^ {i \ pi/2} $ sur $ \ket {001} $ et $-e ^ {i \ pi/2} $ sur $ \ket {101} $ et $ \ket {011} $.</span><span class="sxs-lookup"><span data-stu-id="86034-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="86034-115">Le Voisint est également une approche Measure-and-Fixup qui est l’inverse de l’opération d’origine uniquement dans des cas spéciaux (voir références), mais utilise moins de portes T.</span><span class="sxs-lookup"><span data-stu-id="86034-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="86034-116">Références</span><span class="sxs-lookup"><span data-stu-id="86034-116">References</span></span>

- [<span data-ttu-id="86034-117">*Craig Gidney* , 1709,06648</span><span class="sxs-lookup"><span data-stu-id="86034-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)