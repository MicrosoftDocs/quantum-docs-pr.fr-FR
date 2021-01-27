---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: 1cf2bd944b4dcaadeeca96fa0f576250590962e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827592"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn fonction)

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fonction pour les opérations de récupération Pauli pour une mesure de syndrome donnée par recherche de table pour le code de retournement ⟦ 3, 1 ⟧ bits.

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Sortie : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Fonction de type `RecoveryFn` qui prend une mesure de syndrome `Result[]` et retourne les `Pauli[]` opérations qui corrigent l’erreur détectée.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)