---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpObliviousByOraclePhases
title: AmpAmpObliviousByOraclePhases fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpObliviousByOraclePhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpObliviousByOraclePhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfromstatepreparation".
ms.openlocfilehash: eb1b03b26848eada800ead999804c214d7f09ef8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706566"
---
# <a name="ampampobliviousbyoraclephases-function"></a><span data-ttu-id="9ae7d-102">AmpAmpObliviousByOraclePhases fonction)</span><span class="sxs-lookup"><span data-stu-id="9ae7d-102">AmpAmpObliviousByOraclePhases function</span></span>

<span data-ttu-id="9ae7d-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="9ae7d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="9ae7d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ae7d-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="9ae7d-105">AmpAmpObliviousByOraclePhases est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="9ae7d-105">AmpAmpObliviousByOraclePhases has been deprecated.</span></span> <span data-ttu-id="9ae7d-106">Utilisez plutôt <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation>.</span><span class="sxs-lookup"><span data-stu-id="9ae7d-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation> instead.</span></span>
>
> <span data-ttu-id="9ae7d-107">Utilisez @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfromstatepreparation".</span><span class="sxs-lookup"><span data-stu-id="9ae7d-107">Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfromstatepreparation".</span></span>



```qsharp
function AmpAmpObliviousByOraclePhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9ae7d-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="9ae7d-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="9ae7d-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="9ae7d-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="9ae7d-110">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="9ae7d-110">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>




### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="9ae7d-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="9ae7d-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="9ae7d-112">idxFlagQubit : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ae7d-112">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="9ae7d-113">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="9ae7d-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

