---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Opération DiscretePhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703654"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="61cab-102">Opération DiscretePhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="61cab-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="61cab-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="61cab-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="61cab-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="61cab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="61cab-105">Exécute une seule itération d’un algorithme d’estimation de phase itérative (contrôlée de manière classique) à l’aide des puissances de nombre entier d’une entité Oracle.</span><span class="sxs-lookup"><span data-stu-id="61cab-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="61cab-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="61cab-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="61cab-107">Oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="61cab-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="61cab-108">Opération agissant sur un entier et un registre, de sorte que $U ^ m $ est appliqué au registre donné, où $U $ est l’unité de temps dont la phase doit être estimée, et où $m est la puissance de l’entier accordée à Oracle.</span><span class="sxs-lookup"><span data-stu-id="61cab-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="61cab-109">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="61cab-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="61cab-110">Nombre de fois où l’application Oracle unitaire donnée est appliquée.</span><span class="sxs-lookup"><span data-stu-id="61cab-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="61cab-111">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="61cab-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="61cab-112">Angle d’inversion de la phase sur le contrôle qubit avant d’agir sur l’État cible.</span><span class="sxs-lookup"><span data-stu-id="61cab-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="61cab-113">targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="61cab-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="61cab-114">Registre d’état traité par l’entité Oracle donnée.</span><span class="sxs-lookup"><span data-stu-id="61cab-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="61cab-115">controlQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="61cab-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="61cab-116">Qubit auxiliaire utilisé pour contrôler l’application du Oracle donné.</span><span class="sxs-lookup"><span data-stu-id="61cab-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61cab-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61cab-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
