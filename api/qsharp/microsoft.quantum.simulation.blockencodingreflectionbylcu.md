---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: b8eff9d207752213ccdf42a9ad80fefb2da07216
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708615"
---
# <a name="blockencodingreflectionbylcu-function"></a>BlockEncodingReflectionByLCU fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Encode un opérateur d’intérêt dans un `BlockEncodingReflection` .

Cela crée une `BlockEncodingReflection` unité de $U = P\cdot V\cdot P ^ \dagger $ qui encode un opérateur $H = \ sum_ {j} | \ alpha_j | U_j $ d’intérêt qui est une combinaison linéaire de divisions. En général, $P $ est une unité de préparation de l’État, telle que $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ et $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Entrée

### <a name="statepreparation--qubit--unit-adj--ctl"></a>statePreparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL

Un $P unitaire $ qui prépare un État cible.


### <a name="selector--qubitqubit--unit-adj--ctl"></a>sélecteur : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL

$V unitaire $ qui encode les unités de composants de $H $.



## <a name="output--blockencodingreflection"></a>Sortie : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Une unité de $U $ agissant conjointement sur les registres `a` et `s` qui encode le bloc $H $ et satisfait $U' ^ {-1} = U $.

## <a name="remarks"></a>Notes

Cette `BlockEncoding` implémentation lui attribue les propriétés d’un `BlockEncodingReflection` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)