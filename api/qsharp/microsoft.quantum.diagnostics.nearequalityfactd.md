---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702616"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Déclare qu’une valeur à virgule flottante classique a la valeur attendue jusqu’à une petite tolérance de 1e-10.

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>Entrée

### <a name="actual--double"></a>réel : [double](xref:microsoft.quantum.lang-ref.double)

Nombre à vérifier.


### <a name="expected--double"></a>ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)

Valeur attendue.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cela équivaut à une <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> tolérance codée en dur de $10 ^ {-10} $.