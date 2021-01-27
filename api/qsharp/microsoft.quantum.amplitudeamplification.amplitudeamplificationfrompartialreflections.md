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
# <a name="amplitudeamplificationfrompartialreflections-function"></a>AmplitudeAmplificationFromPartialReflections fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Amplification de l’amplitude par réflexions partielles.

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="phases--reflectionphases"></a>phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Phases de réflexions partielles


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Opérateur de réflexion à propos de l’état de démarrage


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Opérateur de réflexion à propos de l’État cible



## <a name="output--qubit--unit--is-adj--ctl"></a>Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération qui implémente l’amplification d’amplitude par réflexions partielles.

## <a name="remarks"></a>Notes

L’amplification d’amplitude est un cas spécial d’amplification de l’amplitude oublie où il n’y a pas de qubits système et le oublie Oracle est défini sur l’identité.
Dans la plupart des cas, `startQubits` est initialisé dans l’État $ \ket{\text{start}} \_ $1, qui est le eigenstate $-$1 de `startStateReflection` .