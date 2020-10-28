---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Opération MeasureStabilizerGenerators
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702451"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="72690-102">Opération MeasureStabilizerGenerators</span><span class="sxs-lookup"><span data-stu-id="72690-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="72690-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="72690-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="72690-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72690-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72690-105">Mesure le jeu de générateurs donné d’un groupe stabilisant.</span><span class="sxs-lookup"><span data-stu-id="72690-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="72690-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="72690-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="72690-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="72690-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="72690-108">Tableau d’opérateurs Pauli multiqubit.</span><span class="sxs-lookup"><span data-stu-id="72690-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="72690-109">Par exemple, `stabilizerGroup[0]` est une liste de matrices Pauli à qubit unique, dont le produit tenseur est un générateur stabilisant.</span><span class="sxs-lookup"><span data-stu-id="72690-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="72690-110">logicalRegister : [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="72690-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="72690-111">Tableau de qubits où le code stabilisant est défini.</span><span class="sxs-lookup"><span data-stu-id="72690-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="72690-112">Gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="72690-112">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="72690-113">Opération qui spécifie comment mesurer un opérateur multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="72690-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="72690-114">Sortie : [syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="72690-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="72690-115">Résultat des mesures.</span><span class="sxs-lookup"><span data-stu-id="72690-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="72690-116">Notes</span><span class="sxs-lookup"><span data-stu-id="72690-116">Remarks</span></span>

<span data-ttu-id="72690-117">Cela ne vérifie pas si l’ensemble donné de générateurs se transporte.</span><span class="sxs-lookup"><span data-stu-id="72690-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="72690-118">Dans le cas contraire, le résultat des mesures peut être arbitraire.</span><span class="sxs-lookup"><span data-stu-id="72690-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>