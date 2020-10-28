---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702394"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX fonction)

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


Décodeur de la partie X du groupe stabilisant du code Quantum ⟦ 7, 1, 3 ⟧ Steane.

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>Entrée

### <a name="syndrome--syndrome"></a>syndrome : [syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Tableau de syndromes obtenu à partir de la mesure de la partie X du stabilisateur.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tableau d’opérations Pauli qui, lorsqu’il est appliqué au système Quantum encodé, corrige l’erreur correspondant à `syndrome` .

## <a name="remarks"></a>Notes

Le décodeur choisi utilise la propriété de code CSS du code Steane ⟦ 7, 1, 3 ⟧, c.-à-d., il corrige les erreurs X et Z séparément. Une propriété du code est que l’emplacement de la correction Z, respectivement, à appliquer est l’encodage 3 bits du X, respectivement, le syndrome Z lorsqu’il est considéré comme un entier.

## <a name="references"></a>Références

- D. Gottesman, « codes stabilisants et correction des erreurs Quantum », doctorat. thèse, Caltech, 1997 ; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)