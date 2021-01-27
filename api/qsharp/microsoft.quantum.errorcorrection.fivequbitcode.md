---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853142"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode fonction)

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une valeur QECC représentant l’encodeur de code ⟦ 5, 1, 3 ⟧ et un décodeur avec mesure de la syndrome sur place.

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>Sortie : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Retourne une implémentation d’un code de correction d’erreur de Quantum en spécifiant un `QECC` type.

## <a name="remarks"></a>Notes

Ce code a été trouvé indépendamment dans les deux documents suivants :

- C. H. Bennett, D. DiVincenzo, J. A. Smolin et W. K. Wootters, « enchevêtrement d’État mixte et correction d’erreur quantique », «phys. Rev. A, 54 (1996) pp. 3824-3851 ; https://arxiv.org/abs/quant-ph/9604024 et
- R. Laflamme, C. Miquel, J. P. Paz et W. H. Zurek, « code de correction d’erreur quantique parfait », « phys. Rev. Lett ». 77 (1996) pp. 198-201 ; https://arxiv.org/abs/quant-ph/9602019