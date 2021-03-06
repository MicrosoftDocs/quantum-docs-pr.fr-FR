---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Opération IncrementByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846600"
---
# <a name="incrementbymodularinteger-operation"></a>Opération IncrementByModularInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Effectue un incrément modulaire d’un registre qubit à l’aide d’une constante entière.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
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