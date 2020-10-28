---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Opération ApplyToLittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: d94a9969a3f827d594946ab8ca6cd4672da7ef7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708696"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="f6d11-102">Opération ApplyToLittleEndian</span><span class="sxs-lookup"><span data-stu-id="f6d11-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="f6d11-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f6d11-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f6d11-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6d11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6d11-105">Applique une opération au qubits sous-jacent qui constitue un registre Little endian.</span><span class="sxs-lookup"><span data-stu-id="f6d11-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="f6d11-106">Cette opération est marquée comme interne, car un registre Little endian est destiné à être « opaque », de sorte qu’il ne s’agit que d’un détail d’implémentation.</span><span class="sxs-lookup"><span data-stu-id="f6d11-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="f6d11-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="f6d11-107">Input</span></span>

### <a name="bareop--qubit--unit-adj--ctl"></a><span data-ttu-id="f6d11-108">bareOp : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="f6d11-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="f6d11-109">inscription : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f6d11-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="f6d11-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6d11-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

