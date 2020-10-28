---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Opération IncrementByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707262"
---
# <a name="incrementbymodularinteger-operation"></a>Opération IncrementByModularInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Effectue un incrément modulaire d’un registre qubit à l’aide d’une constante entière.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Description

Faites-nous part `increment` de $a $, `modulus` de $N $ et de l’entier encodé dans `target` par $y $.
L’opération effectue ensuite la transformation suivante : \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} entiers sont encodés au format Little endian.

## <a name="input"></a>Entrée

### <a name="increment--int"></a>incrément : [entier](xref:microsoft.quantum.lang-ref.int)

Incrément entier $a $ à ajouter à $y $.


### <a name="modulus--int"></a>modulo : [entier](xref:microsoft.quantum.lang-ref.int)

Entier $N $ mods $y + a $.


### <a name="target--littleendian"></a>cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Entier $y $ dans le `LittleEndian` format auquel `increment` $a $ est ajouté.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Suppose que la valeur initiale de Target est inférieure à $N $ et que l’incrément $a $ est inférieur à $N $.
Notez que <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implémente la même opération dans la `PhaseLittleEndian` base.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. IncrementPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)