---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827909"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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