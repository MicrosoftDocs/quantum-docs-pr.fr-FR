---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701776"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>_IdentityTimeDependentGeneratorSystem fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Retourne un système de générateur conforme à la valeur de la propriété Hamilton `H(s) = 0` , où `s` est un paramètre de planification.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrée

### <a name="schedule--double"></a>planification : [double](xref:microsoft.quantum.lang-ref.double)

Cette entrée est ignorée et est définie pour une cohérence avec le <xref:microsoft.quantum.canon.timedependentgeneratorsystem> type défini par l’utilisateur.



## <a name="output--generatorsystem"></a>Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Un système de générateur représentant l’évolution sous la $H de la Hamilton (s) = $0 pour tous les $s $.