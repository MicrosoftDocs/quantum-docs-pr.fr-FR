---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Opération SelectZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703105"
---
# <a name="selectz-operation"></a><span data-ttu-id="1f16b-102">Opération SelectZ</span><span class="sxs-lookup"><span data-stu-id="1f16b-102">SelectZ operation</span></span>

<span data-ttu-id="1f16b-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1f16b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1f16b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f16b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f16b-105">$U unitaire $ qui applique le Pauli $Z $ Gate sur un qubits $p $ conditionné sur un état d’index $ \ket{p} $.</span><span class="sxs-lookup"><span data-stu-id="1f16b-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="1f16b-106">Autrement dit, $ $ \begin{align} U\ket {p} \ Ket {\ PSI} = \ket{p}Z \_ p\ket {\ PSI} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="1f16b-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1f16b-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="1f16b-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="1f16b-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1f16b-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1f16b-109">L’État $ \ket{p} $ de ce registre détermine le qubit sur lequel $Z $ est appliqué.</span><span class="sxs-lookup"><span data-stu-id="1f16b-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="1f16b-110">targetRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f16b-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f16b-111">Registre de qubits sur lequel les opérateurs Pauli sont appliqués.</span><span class="sxs-lookup"><span data-stu-id="1f16b-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f16b-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f16b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

