---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214277"
---
# <a name="boolarrayaspauli-function"></a>BoolArrayAsPauli fonction)

Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dans le cas d’une chaîne binaire, retourne un opérateur Pauli qubit multiple représenté sous la forme d’un tableau d’opérateurs Pauli qubit uniques.

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>Entrée

### <a name="pauli--pauli"></a>Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Opérateur Pauli à appliquer à qubits où `bitsApply == bits[idx]` .


### <a name="bitapply--bool"></a>bitApply : [bool](xref:microsoft.quantum.lang-ref.bool)

Appliquez Pauli si bit est cette valeur.


### <a name="bits--bool"></a>bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tableau booléen.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>Notes

Le tableau booléen et le registre Quantum doivent être de longueur égale.