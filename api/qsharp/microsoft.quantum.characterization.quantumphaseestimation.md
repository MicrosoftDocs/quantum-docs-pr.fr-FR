---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Opération QuantumPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 7e524477a4b2bcd8d6767441e278fbf501355e0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703600"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="c9981-102">Opération QuantumPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="c9981-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="c9981-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="c9981-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="c9981-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9981-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9981-105">Exécute l’algorithme d’estimation de phase quantique pour un Oracle donné `U` et `targetState` , en lisant la phase dans un registre quantique Big-endian.</span><span class="sxs-lookup"><span data-stu-id="c9981-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="c9981-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c9981-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="c9981-107">Oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="c9981-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="c9981-108">Une opération qui implémente $U ^ m $ pour les nombres entiers fournis est de m.</span><span class="sxs-lookup"><span data-stu-id="c9981-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="c9981-109">targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c9981-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c9981-110">Un registre quantique représentant l’État $ \ket{\Phi} $ traité par $U $.</span><span class="sxs-lookup"><span data-stu-id="c9981-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="c9981-111">Si $ \ket{\Phi} $ est un eigenstate de $U $, $U \ket{\Phi} = e ^ {i\phi} \ket{\Phi} $ pour $ \Phi \Dans [0, 2 \ pi) $ une phase inconnue.</span><span class="sxs-lookup"><span data-stu-id="c9981-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="c9981-112">controlRegister : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="c9981-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="c9981-113">Registre d’entiers de représentation Big endian qui peut être utilisé pour contrôler le Oracle fourni, et qui contient la représentation de $ \Phi $ à la suite de l’application de cette opération.</span><span class="sxs-lookup"><span data-stu-id="c9981-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="c9981-114">Le controlRegister est supposé démarrer à l’état initial $ \ket{00\cdots 0} $, où la longueur du registre indique la précision souhaitée.</span><span class="sxs-lookup"><span data-stu-id="c9981-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9981-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9981-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
