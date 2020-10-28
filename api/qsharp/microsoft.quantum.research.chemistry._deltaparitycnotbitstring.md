---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701845"
---
# <a name="_deltaparitycnotbitstring-function"></a>_DeltaParityCNOTbitstring fonction)

Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)

Packages [](https://nuget.org/packages/)


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