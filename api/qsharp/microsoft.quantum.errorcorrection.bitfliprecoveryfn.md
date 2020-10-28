---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702550"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn fonction)

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


Fonction pour les opérations de récupération Pauli pour une mesure de syndrome donnée par recherche de table pour le code de retournement ⟦ 3, 1 ⟧ bits.

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Sortie : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Fonction de type `RecoveryFn` qui prend une mesure de syndrome `Result[]` et retourne les `Pauli[]` opérations qui corrigent l’erreur détectée.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)