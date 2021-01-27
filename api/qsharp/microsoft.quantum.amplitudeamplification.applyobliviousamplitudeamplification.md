---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: Opération ApplyObliviousAmplitudeAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: c171021272076cc3960307523e25c4493bb49c5a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845874"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>Opération ApplyObliviousAmplitudeAmplification

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Amplification d’amplitude oublie en spécifiant des réflexions partielles.

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="phases--reflectionphases"></a>phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Phases de réflexions partielles


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Opérateur de réflexion à propos de l’état de démarrage du Registre auxiliaire


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Opérateur de réflexion sur l’État cible du Registre auxiliaire


### <a name="signaloracle--obliviousoracle"></a>signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Oracle $O $ unitaire `ObliviousOracle` qui agit conjointement aux registres auxiliaires et système.


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre auxiliaire


### <a name="systemregister--qubit"></a>systemRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre système



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Étant donné un état de démarrage auxiliaire particulier $ \ket{\text{Start}} \_ a $, un État cible auxiliaire particulier $ \ket{\text{Target}} \_ a $ et tout état système $ \ket{\Psi} \_ s $, supposons que \begin{align} O\ket {\ Text {Start}} \_ a\ket {\ PSI} \_ s = \lambda\ket{\text{Target}} \_ a U \ket{\Psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{Target} ^ \perp} \_ a\cdots \end{align} pour une unité $U $.
Par une séquence de réflexions sur les États de démarrage et de cible sur le registre auxiliaire entrelacé par les applications de `signalOracle` et ses voisins, la probabilité de réussite de l’application de U peut être modifiée.

Dans la plupart des cas, `auxiliaryRegister` est initialisé dans l’État $ \ket{\text{Start}} \_ a $.

## <a name="references"></a>Références

Consultez

- [ *D.W. Berry, A.M. Childs, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) pour la version standard.
  Consultez
- [ *G.H. Low, I.L. Chuang*](https://arxiv.org/abs/1610.06546) pour une généralisation à des réflexions partielles.