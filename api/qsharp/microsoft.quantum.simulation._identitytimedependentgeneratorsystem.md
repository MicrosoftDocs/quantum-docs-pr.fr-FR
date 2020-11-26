---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225599"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>_IdentityTimeDependentGeneratorSystem fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne un système de générateur conforme à la valeur de la propriété Hamilton `H(s) = 0` , où `s` est un paramètre de planification.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrée

### <a name="schedule--double"></a>planification : [double](xref:microsoft.quantum.lang-ref.double)

Cette entrée est ignorée et est définie pour une cohérence avec le <xref:microsoft.quantum.canon.timedependentgeneratorsystem> type défini par l’utilisateur.



## <a name="output--generatorsystem"></a>Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Un système de générateur représentant l’évolution sous la $H de la Hamilton (s) = $0 pour tous les $s $.