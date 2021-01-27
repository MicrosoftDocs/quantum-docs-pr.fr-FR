---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856830"
---
# <a name="purifiedmixedstaterequirements-function"></a>PurifiedMixedStateRequirements fonction)

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne le nombre total de qubits qui doivent être alloués afin d’appliquer l’opération retournée par @"microsoft.quantum.preparation.purifiedmixedstate" .

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>Entrée

### <a name="targeterror--double"></a>targetError : [double](xref:microsoft.quantum.lang-ref.double)

L’erreur cible $ \epsilon $.


### <a name="ncoefficients--int"></a>nCoefficients : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de coefficients à spécifier dans la préparation d’un État mixte.



## <a name="output--mixedstatepreparationrequirements"></a>Sortie : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

Description du nombre total de qubits requis et pour chacun des registres d’index et de nettoyage de la mémoire utilisés par la @"microsoft.quantum.preparation.purifiedmixedstate" fonction.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PREPARATION. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)