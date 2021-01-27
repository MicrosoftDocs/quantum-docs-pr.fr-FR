---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843925"
---
# <a name="standardamplitudeamplification-function"></a>StandardAmplitudeAmplification fonction)

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Algorithme d’amplification d’amplitude standard

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="niterations--int"></a>nIterations : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’itérations $n $ d’amplification d’amplitude


### <a name="stateoracle--stateoracle"></a>stateOracle : [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

$A Oracle unitaire $ qui prépare l’état de démarrage


### <a name="idxflagqubit--int"></a>idxFlagQubit : [entier](xref:microsoft.quantum.lang-ref.int)

Index pour marquer qubit



## <a name="output--qubit--unit--is-adj--ctl"></a>Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération qui implémente l’algorithme Quantum d’amplification d’amplitude standard

## <a name="remarks"></a>Notes

Il s’agit de l’algorithme d’amplification d’amplitude standard obtenu par un choix de phases de réflexion calculées en `AmpAmpPhasesStandard` supposant que \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} cette opération prépare l’État \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket {1} \_ f\ket {\ Text {target}} \_ s + \cdots\ket {0} \_ f \end{align} dans la plupart des cas, `flagQubit` et `auxiliaryRegister` est initialisé dans l’État $ \ket {0} \_ f\ket {0} \_ a $.

## <a name="references"></a>Références

- [*G. Brassard, P. Hoyer, M. Mosca, A. Tapp*](https://arxiv.org/abs/quant-ph/0005055)