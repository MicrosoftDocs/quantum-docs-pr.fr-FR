---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: e64ad5ad4e975483f20f92c0b070dd6788ef296b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847451"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a>AmplitudeAmplificationFromStatePreparation fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="output--qubit--unit--is-adj--ctl"></a>Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération qui implémente l’amplification d’amplitude par Oracle implémenté par des réflexions partielles.

## <a name="remarks"></a>Notes

Cela impose des conditions plus strictes sous forme d’États de démarrage et de cible que dans `AmpAmpByReflectionPhases` .
Il est supposé que l’État cible est marqué par $ \ket {1} \_ f $.
Il est supposé que \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} dans la plupart des cas, `flagQubit` et `auxiliaryRegister` sont initialisés à l’État $ \ket {0} \_ {f} \ket {0} \_ s $.