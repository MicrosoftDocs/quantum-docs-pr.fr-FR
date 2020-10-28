---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702658"
---
# <a name="equalitywithintolerancefact-function"></a>EqualityWithinToleranceFact fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Représente la revendication selon laquelle une valeur à virgule flottante classique a la valeur attendue jusqu’à une tolérance absolue donnée.

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>Entrée

### <a name="actual--double"></a>réel : [double](xref:microsoft.quantum.lang-ref.double)

Nombre à vérifier.


### <a name="expected--double"></a>ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)

Valeur attendue.


### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance absolue sur la différence entre réel et attendu.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

