---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226075"
---
# <a name="_deltaparitycnotbitstring-function"></a>_DeltaParityCNOTbitstring fonction)

Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)

Package : [Microsoft. Quantum. Research. chimie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Étape de traitement classique de `ApplyDeltaParity` .
Cela calcule une liste de qubits de contrôle pour l’évaluation de la différence de parité entre deux PQRS... termes de longueur égale.

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>Entrée

### <a name="prevfermionicterm--int"></a>prevFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>nextFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])



## <a name="remarks"></a>Notes

Cela suppose que la longueur des termes est égale à.
Calcule la liste des contrôles pour la différence de parité entre deux termes quelconques.
Cela suppose que les listes d’entrée sont triées dans l’ordre croissant.