---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707769"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a>AmplitudeAmplificationFromStatePreparation fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Packages [](https://nuget.org/packages/)


Amplification d’amplitude par Oracle pour les réflexions partielles.

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="phases--reflectionphases"></a>phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Phases de réflexions partielles


### <a name="stateoracle--stateoracle"></a>stateOracle : [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

$A Oracle unitaire $ qui prépare l’état de démarrage


### <a name="idxflagqubit--int"></a>idxFlagQubit : [entier](xref:microsoft.quantum.lang-ref.int)

Index pour marquer qubit



## <a name="output--qubit--unit-adj--ctl"></a>Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL

Opération qui implémente l’amplification d’amplitude par Oracle implémenté par des réflexions partielles.

## <a name="remarks"></a>Notes

Cela impose des conditions plus strictes sous forme d’États de démarrage et de cible que dans `AmpAmpByReflectionPhases` .
Il est supposé que l’État cible est marqué par $ \ket {1} \_ f $.
Il est supposé que \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} dans la plupart des cas, `flagQubit` et `auxiliaryRegister` sont initialisés à l’État $ \ket {0} \_ {f} \ket {0} \_ s $.