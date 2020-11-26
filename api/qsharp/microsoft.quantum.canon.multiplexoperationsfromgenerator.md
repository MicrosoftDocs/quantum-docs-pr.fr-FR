---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Opération MultiplexOperationsFromGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 9fbbd9268d4a6b9f3d5fd203969f4bbeebe81b68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205947"
---
# <a name="multiplexoperationsfromgenerator-operation"></a>Opération MultiplexOperationsFromGenerator

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération unitaire contrôlée par multiplication $U $ qui applique une $V unitaire _j $ lorsqu’elle est contrôlée par le numéro d’État n-qubit $ \ket{j} $.

$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a>unitaryGenerator : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL)

Tuple où le premier élément `Int` est le nombre d’unités de $N $, et le deuxième élément `(Int -> ('T => () is Adj + Ctl))` est une fonction qui accepte un entier $j $ dans $ [0, N-1] $ et génère l’opération unitaire $V _J $.


### <a name="index--littleendian"></a>index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.


### <a name="target--t"></a>cible : 't

Registre qubit générique sur lequel $V _j $ agit.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

`coefficients` sera complété avec les éléments d’identité si moins de $2 ^ n $ sont spécifiés. Cette implémentation utilise $n-$1 auxiliaire qubits.

## <a name="references"></a>Références

- [*Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su*, arXiv : 1711.10980](https://arxiv.org/abs/1711.10980)