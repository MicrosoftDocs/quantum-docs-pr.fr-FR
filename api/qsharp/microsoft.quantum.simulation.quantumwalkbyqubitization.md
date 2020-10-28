---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709326"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="bdf31-102">QuantumWalkByQubitization fonction)</span><span class="sxs-lookup"><span data-stu-id="bdf31-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="bdf31-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bdf31-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bdf31-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bdf31-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bdf31-105">Convertit une réflexion d’encodage de bloc en un parcours quantique.</span><span class="sxs-lookup"><span data-stu-id="bdf31-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="bdf31-106">Description</span><span class="sxs-lookup"><span data-stu-id="bdf31-106">Description</span></span>

<span data-ttu-id="bdf31-107">À partir d’un `BlockEncodingReflection` représenté par un $U unitaire $ qui encode un opérateur $H $ d’intérêt, le convertit en un parcours quantique $W $ contenant le spectre de $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="bdf31-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="bdf31-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="bdf31-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="bdf31-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="bdf31-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="bdf31-110">`BlockEncodingReflection`$U unitaire $ à convertir en un parcours quantique.</span><span class="sxs-lookup"><span data-stu-id="bdf31-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="bdf31-111">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="bdf31-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bdf31-112">Un parcours quantique $W $ agissant conjointement sur les registres `a` et `s` qui encodent en bloc $H $ et contient le spectre de $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="bdf31-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="bdf31-113">Références</span><span class="sxs-lookup"><span data-stu-id="bdf31-113">References</span></span>

- <span data-ttu-id="bdf31-114">Simulation de la Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="bdf31-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="bdf31-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bdf31-115">See Also</span></span>

- [<span data-ttu-id="bdf31-116">Microsoft. Quantum. simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="bdf31-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="bdf31-117">Microsoft. Quantum. simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="bdf31-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)