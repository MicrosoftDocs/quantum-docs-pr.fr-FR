---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203941"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString fonction)

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Calcule le composant Z de Jordanie – chaîne Wigner entre les index fermion dans un opérateur fermionic avec un nombre pair d’opérateurs de création/annihilation.

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a>Entrée

### <a name="nfermions--int"></a>nFermions : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de fermions dans le système.


### <a name="idxfermions--int"></a>idxFermions : [int](xref:microsoft.quantum.lang-ref.int)[]

indices d’opérateur fermionic.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Bitstring `Bool[]` `true` où un `PauliZ` doit être appliqué.