---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703024"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="313d1-102">BoolArrayAsPauli fonction)</span><span class="sxs-lookup"><span data-stu-id="313d1-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="313d1-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="313d1-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="313d1-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="313d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="313d1-105">Dans le cas d’une chaîne binaire, retourne un opérateur Pauli qubit multiple représenté sous la forme d’un tableau d’opérateurs Pauli qubit uniques.</span><span class="sxs-lookup"><span data-stu-id="313d1-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="313d1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="313d1-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="313d1-107">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="313d1-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="313d1-108">Opérateur Pauli à appliquer à qubits où `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="313d1-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="313d1-109">bitApply : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="313d1-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="313d1-110">Appliquez Pauli si bit est cette valeur.</span><span class="sxs-lookup"><span data-stu-id="313d1-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="313d1-111">bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="313d1-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="313d1-112">Tableau booléen.</span><span class="sxs-lookup"><span data-stu-id="313d1-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="313d1-113">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="313d1-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="313d1-114">Notes</span><span class="sxs-lookup"><span data-stu-id="313d1-114">Remarks</span></span>

<span data-ttu-id="313d1-115">Le tableau booléen et le registre Quantum doivent être de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="313d1-115">The Boolean array and the quantum register must be of equal length.</span></span>