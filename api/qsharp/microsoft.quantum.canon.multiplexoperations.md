---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Opération MultiplexOperations
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703981"
---
# <a name="multiplexoperations-operation"></a>Opération MultiplexOperations

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique un tableau d’opérations contrôlé par un tableau d’États de nombre.

Autrement dit, applique une opération unitaire contrôlée par multiplication $U $ qui applique une $V unitaire _j $ lorsqu’elle est contrôlée par $n $-qubit Number State $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Entrée

### <a name="unitaries--t--unit-adj--ctl"></a>unités : 't [=> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL []

Tableau allant jusqu’à $2 ^ n $ opérations unitaires. Le $j $ th opération est indexé par le nombre d’États $ \ket{j} $ encodé au format Little endian.


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

- Vers la première simulation de Quantum avec accélération de Quantum Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su https://arxiv.org/abs/1711.10980