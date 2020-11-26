---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 30e1cf6e353b8a4491e13a9e2f588ec9cc103cb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191599"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="0cf40-102">AmplitudeAmplificationFromStatePreparation fonction)</span><span class="sxs-lookup"><span data-stu-id="0cf40-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="0cf40-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="0cf40-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="0cf40-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0cf40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0cf40-105">Amplification d’amplitude par Oracle pour les réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="0cf40-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="0cf40-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0cf40-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="0cf40-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="0cf40-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="0cf40-108">Phases de réflexions partielles</span><span class="sxs-lookup"><span data-stu-id="0cf40-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="0cf40-109">stateOracle : [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="0cf40-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="0cf40-110">$A Oracle unitaire $ qui prépare l’état de démarrage</span><span class="sxs-lookup"><span data-stu-id="0cf40-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="0cf40-111">idxFlagQubit : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0cf40-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0cf40-112">Index pour marquer qubit</span><span class="sxs-lookup"><span data-stu-id="0cf40-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="0cf40-113">Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="0cf40-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0cf40-114">Opération qui implémente l’amplification d’amplitude par Oracle implémenté par des réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="0cf40-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="0cf40-115">Notes</span><span class="sxs-lookup"><span data-stu-id="0cf40-115">Remarks</span></span>

<span data-ttu-id="0cf40-116">Cela impose des conditions plus strictes sous forme d’États de démarrage et de cible que dans `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="0cf40-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="0cf40-117">Il est supposé que l’État cible est marqué par $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="0cf40-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="0cf40-118">Il est supposé que \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} dans la plupart des cas, `flagQubit` et `auxiliaryRegister` sont initialisés à l’État $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="0cf40-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>