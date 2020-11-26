---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Opération ApplyPauliFromBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: cf4c99ec5134fac788cdd4c8a057258790152a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209058"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="d1790-102">Opération ApplyPauliFromBitString</span><span class="sxs-lookup"><span data-stu-id="d1790-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="d1790-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1790-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1790-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1790-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1790-105">Applique un opérateur Pauli sur chaque qubit d’un tableau si le bit correspondant d’un tableau booléen correspond à une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="d1790-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d1790-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d1790-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="d1790-107">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="d1790-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="d1790-108">Opérateur Pauli à appliquer à `qubits[idx]` Where `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="d1790-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="d1790-109">bitApply : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d1790-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d1790-110">appliquer Pauli si le bit est cette valeur</span><span class="sxs-lookup"><span data-stu-id="d1790-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="d1790-111">bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d1790-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d1790-112">Registre booléen spécifiant le qubit correspondant dans lequel `qubits` doit être traité</span><span class="sxs-lookup"><span data-stu-id="d1790-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d1790-113">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d1790-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d1790-114">Registre quantique sur lequel appliquer de manière sélective l’opérateur Pauli spécifié</span><span class="sxs-lookup"><span data-stu-id="d1790-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1790-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1790-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d1790-116">Notes</span><span class="sxs-lookup"><span data-stu-id="d1790-116">Remarks</span></span>

<span data-ttu-id="d1790-117">Le tableau booléen et le registre Quantum doivent être de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="d1790-117">The Boolean array and the quantum register must be of equal length.</span></span>