---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709020"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Encode un opérateur d’intérêt dans un `BlockEncoding` .

Cela crée une `BlockEncoding` unité de $U = P\cdot V\cdot P ^ \dagger $ qui encode un opérateur $H = \ sum_ {j} | \ alpha_j | U_j $ d’intérêt qui est une combinaison linéaire de divisions. En règle générale, $P $ est une unité de préparation de l’État, telle que $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ et $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL

Un $P unitaire $ qui prépare un État cible.


### <a name="selector--ts--unit-adj--ctl"></a>sélecteur : ('t, 's) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL

$V unitaire $ qui encode les unités de composants de $H $.



## <a name="output--ts--unit-adj--ctl"></a>Sortie : ('t, ') => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL

Un $U unitaire $ agissant conjointement sur `a` les registres et `s` qui encodent les blocs $H $ et satisfont $U ^ \Dagger = U $.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="s"></a>Examin



## <a name="remarks"></a>Notes

Cette `BlockEncoding` implémentation lui attribue les propriétés d’un `BlockEncodingReflection` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)