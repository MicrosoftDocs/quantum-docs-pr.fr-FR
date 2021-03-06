---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834250"
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