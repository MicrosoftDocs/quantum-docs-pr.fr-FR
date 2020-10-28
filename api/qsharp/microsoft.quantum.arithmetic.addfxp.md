---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Opération AddFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707662"
---
# <a name="addfxp-operation"></a>Opération AddFxP

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Ajoute deux nombres à virgule fixe stockés dans des registres quantiques.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a>Description

À partir de deux registres à virgule fixe respectivement dans les États $ \ket{f_1} $ et $ \ket{f_2} $, exécute l’opération $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.

## <a name="input"></a>Entrée

### <a name="fp1--fixedpoint"></a>FP1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Premier nombre à virgule fixe


### <a name="fp2--fixedpoint"></a>FP2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Deuxième nombre à virgule fixe, sera mis à jour pour contenir la somme des deux entrées.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Dans l’implémentation actuelle, les deux nombres à virgule fixe doivent avoir la même position de point que le bit le moins significatif, c.-à-d. $n _i $ et $p _i $ doit être égal.