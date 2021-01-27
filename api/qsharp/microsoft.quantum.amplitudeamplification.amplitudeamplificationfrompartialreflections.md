---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: e4030aabcab55db35bcb8199e37bee837ead6ad0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845920"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="80b32-102">AmplitudeAmplificationFromPartialReflections fonction)</span><span class="sxs-lookup"><span data-stu-id="80b32-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="80b32-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="80b32-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="80b32-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80b32-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80b32-105">Amplification de l’amplitude par réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="80b32-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="80b32-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="80b32-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="80b32-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="80b32-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="80b32-108">Phases de réflexions partielles</span><span class="sxs-lookup"><span data-stu-id="80b32-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="80b32-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="80b32-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="80b32-110">Opérateur de réflexion à propos de l’état de démarrage</span><span class="sxs-lookup"><span data-stu-id="80b32-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="80b32-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="80b32-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="80b32-112">Opérateur de réflexion à propos de l’État cible</span><span class="sxs-lookup"><span data-stu-id="80b32-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="80b32-113">Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="80b32-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="80b32-114">Opération qui implémente l’amplification d’amplitude par réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="80b32-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="80b32-115">Notes</span><span class="sxs-lookup"><span data-stu-id="80b32-115">Remarks</span></span>

<span data-ttu-id="80b32-116">L’amplification d’amplitude est un cas spécial d’amplification de l’amplitude oublie où il n’y a pas de qubits système et le oublie Oracle est défini sur l’identité.</span><span class="sxs-lookup"><span data-stu-id="80b32-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="80b32-117">Dans la plupart des cas, `startQubits` est initialisé dans l’État $ \ket{\text{start}} \_ $1, qui est le eigenstate $-$1 de `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="80b32-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>