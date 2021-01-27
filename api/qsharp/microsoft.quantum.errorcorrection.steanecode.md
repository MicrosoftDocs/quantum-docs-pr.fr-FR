---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853055"
---
# <a name="steanecode-function"></a>SteaneCode fonction)

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une valeur CSS représentant l’encodeur de code ⟦ 7, 1, 3 ⟧ Steane et le décodeur avec mesure de syndrome sur place.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Sortie : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Objet de type CSS qui collecte toutes les données pertinentes pour effectuer l’encodage et la correction d’erreur pour le code Steane 7, 1, 3 ⟧ ⟦.

## <a name="remarks"></a>Notes

Ce code a été trouvé dans le document suivant :

- R. Steane, « plusieurs interférences de particule et correction d’erreur quantique », proc. Roy. SOC. lond. A452 (1996) pp. 2551 ; https://arxiv.org/abs/quant-ph/9601029.