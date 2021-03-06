---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 873c436d4b8d8efc9dc61c2baba9b0e0f7f09fc2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845821"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Amplification d’amplitude oublie par Oracle pour les réflexions partielles.

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="phases--reflectionphases"></a>phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Phases de réflexions partielles


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

$A Oracle unitaire $ qui prépare l’état de démarrage auxiliaire


### <a name="signaloracle--obliviousoracle"></a>signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Oracle $O $ unitaire `ObliviousOracle` qui agit conjointement sur les registres auxiliaires et système


### <a name="idxflagqubit--int"></a>idxFlagQubit : [entier](xref:microsoft.quantum.lang-ref.int)

Enregistrement d’un indicateur d’index qubit unique



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération qui implémente l’amplification d’amplitude oublie basée sur des réflexions partielles.

## <a name="remarks"></a>Notes

Cela impose des conditions plus strictes sur la forme des États de démarrage et cible auxiliaires que dans `AmpAmpObliviousByReflectionPhases` .
Il est supposé que $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{Start}} \_ {FA} $ prépare l’état de démarrage auxiliaire $ \ket{\text{Start}} \_ {FA} $ à partir de la base de calcul $ \ket {0} \_ f\ket {0} $.
Il est supposé que l’État cible est marqué par $ \ket {1} \_ f $.
Il est supposé que \begin{align} O\ket {\ Text {Start}} \_ {FA} \ket{\Psi} \_ s = \lambda\ket {1} \_ f\ket {\ Text {tout}} \_ a\ket {\ Text {target}} \_ s U \ket{\Psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket f\cdots {0} \_ , \end{align} pour some Unity $U $.