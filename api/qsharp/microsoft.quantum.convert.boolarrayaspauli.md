---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214277"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="a41a8-102">BoolArrayAsPauli fonction)</span><span class="sxs-lookup"><span data-stu-id="a41a8-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="a41a8-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="a41a8-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="a41a8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a41a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a41a8-105">Dans le cas d’une chaîne binaire, retourne un opérateur Pauli qubit multiple représenté sous la forme d’un tableau d’opérateurs Pauli qubit uniques.</span><span class="sxs-lookup"><span data-stu-id="a41a8-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="a41a8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a41a8-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="a41a8-107">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a41a8-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a41a8-108">Opérateur Pauli à appliquer à qubits où `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="a41a8-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="a41a8-109">bitApply : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a41a8-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a41a8-110">Appliquez Pauli si bit est cette valeur.</span><span class="sxs-lookup"><span data-stu-id="a41a8-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="a41a8-111">bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a41a8-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a41a8-112">Tableau booléen.</span><span class="sxs-lookup"><span data-stu-id="a41a8-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="a41a8-113">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a41a8-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="a41a8-114">Notes</span><span class="sxs-lookup"><span data-stu-id="a41a8-114">Remarks</span></span>

<span data-ttu-id="a41a8-115">Le tableau booléen et le registre Quantum doivent être de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="a41a8-115">The Boolean array and the quantum register must be of equal length.</span></span>