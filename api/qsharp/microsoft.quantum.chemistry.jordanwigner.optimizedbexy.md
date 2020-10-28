---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: Opération OptimizedBEXY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 359d347fc57be46200a218646911a7a400b4a96d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703156"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="3f535-102">Opération OptimizedBEXY</span><span class="sxs-lookup"><span data-stu-id="3f535-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="3f535-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3f535-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3f535-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f535-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f535-105">Une $U unitaire $ qui applique la chaîne Pauli sur $ (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 $ sur qubits $0.. p $ conditionné sur un index $z \Dans \{ 0, 1 \} $ et $p $.</span><span class="sxs-lookup"><span data-stu-id="3f535-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="3f535-106">Autrement dit, $ $ \begin{align} U\ket {z} \ Ket {p} \ Ket {\ PSI} = \ket{z}\ket{p} (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\Psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3f535-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3f535-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="3f535-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="3f535-108">pauliBasis : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3f535-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3f535-109">Quand ce qubit est dans l’État $ \ket {0} $, $X $ est appliqué.</span><span class="sxs-lookup"><span data-stu-id="3f535-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="3f535-110">Lorsqu’il est dans l’État $ \ket {1} $, $Y $ est appliqué.</span><span class="sxs-lookup"><span data-stu-id="3f535-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="3f535-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f535-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f535-112">L’État $ \ket{p} $ de ce registre détermine le qubit sur lequel $X $ ou $Y $ est appliqué.</span><span class="sxs-lookup"><span data-stu-id="3f535-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="3f535-113">targetRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3f535-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3f535-114">Registre de qubits sur lequel les opérateurs Pauli sont appliqués.</span><span class="sxs-lookup"><span data-stu-id="3f535-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f535-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f535-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="3f535-116">Références</span><span class="sxs-lookup"><span data-stu-id="3f535-116">References</span></span>

- <span data-ttu-id="3f535-117">Encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pâle, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="3f535-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>