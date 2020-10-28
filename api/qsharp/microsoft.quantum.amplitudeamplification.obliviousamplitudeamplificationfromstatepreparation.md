---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707721"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Packages [](https://nuget.org/packages/)


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



## <a name="output--qubitqubit--unit-adj--ctl"></a>Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL

Opération qui implémente l’amplification d’amplitude oublie basée sur des réflexions partielles.

## <a name="remarks"></a>Notes

Cela impose des conditions plus strictes sur la forme des États de démarrage et cible auxiliaires que dans `AmpAmpObliviousByReflectionPhases` .
Il est supposé que $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{Start}} \_ {FA} $ prépare l’état de démarrage auxiliaire $ \ket{\text{Start}} \_ {FA} $ à partir de la base de calcul $ \ket {0} \_ f\ket {0} $.
Il est supposé que l’État cible est marqué par $ \ket {1} \_ f $.
Il est supposé que \begin{align} O\ket {\ Text {Start}} \_ {FA} \ket{\Psi} \_ s = \lambda\ket {1} \_ f\ket {\ Text {tout}} \_ a\ket {\ Text {target}} \_ s U \ket{\Psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket f\cdots {0} \_ , \end{align} pour some Unity $U $.