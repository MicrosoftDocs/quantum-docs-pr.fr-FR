---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707772"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="4efc6-102">AmplitudeAmplificationFromPartialReflections fonction)</span><span class="sxs-lookup"><span data-stu-id="4efc6-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="4efc6-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="4efc6-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="4efc6-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4efc6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4efc6-105">Amplification de l’amplitude par réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="4efc6-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4efc6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4efc6-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="4efc6-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="4efc6-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="4efc6-108">Phases de réflexions partielles</span><span class="sxs-lookup"><span data-stu-id="4efc6-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="4efc6-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="4efc6-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="4efc6-110">Opérateur de réflexion à propos de l’état de démarrage</span><span class="sxs-lookup"><span data-stu-id="4efc6-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="4efc6-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="4efc6-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="4efc6-112">Opérateur de réflexion à propos de l’État cible</span><span class="sxs-lookup"><span data-stu-id="4efc6-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="4efc6-113">Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="4efc6-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4efc6-114">Opération qui implémente l’amplification d’amplitude par réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="4efc6-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="4efc6-115">Notes</span><span class="sxs-lookup"><span data-stu-id="4efc6-115">Remarks</span></span>

<span data-ttu-id="4efc6-116">L’amplification d’amplitude est un cas spécial d’amplification de l’amplitude oublie où il n’y a pas de qubits système et le oublie Oracle est défini sur l’identité.</span><span class="sxs-lookup"><span data-stu-id="4efc6-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="4efc6-117">Dans la plupart des cas, `startQubits` est initialisé dans l’État $ \ket{\text{start}} \_ $1, qui est le eigenstate $-$1 de `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="4efc6-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>