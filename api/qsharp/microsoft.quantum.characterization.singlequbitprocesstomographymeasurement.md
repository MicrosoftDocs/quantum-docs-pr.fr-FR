---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Opération SingleQubitProcessTomographyMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703591"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>Opération SingleQubitProcessTomographyMeasurement

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Packages [](https://nuget.org/packages/)


Effectue une mesure de tomographie de processus qubit unique dans la base de Pauli, en fonction d’un canal d’intérêt particulier.

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>Entrée

### <a name="preparation--pauli"></a>préparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

L’élément de base Pauli $P $ dans lequel un qubit doit être préparé.


### <a name="measurement--pauli"></a>mesure : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

L’élément de base Pauli $Q $ dans lequel un qubit doit être mesuré.


### <a name="channel--qubit--unit"></a>canal : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [unité](xref:microsoft.quantum.lang-ref.unit) qubit 

Un canal qubit unique $ \Lambda $ dont le comportement est estimé avec la tomographie de processus.



## <a name="output--__invalidresult__"></a>Sortie : __non <Result> valide__

Le résultat `Zero` avec la probabilité $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda ; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).
\end{align} $ $

## <a name="remarks"></a>Notes

La distribution sur les résultats retournés par cette opération est un cas spécial de tomographie d’État à deux qubit. Laissez $ \rho = J (\Lambda)/$2 être l’État Choi – Jamiłkowski pour $ \Lambda $. La distribution ci-dessus est alors identique à $ $ \begin{align} \Pr (\texttt{Zero} | \rho ; M) = \operatorname{Tr} (M \rho), \end{align} $ $ WHERE $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 est la mesure effective correspondant à $P $ et $Q $.