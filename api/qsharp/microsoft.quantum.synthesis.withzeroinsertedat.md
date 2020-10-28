---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709146"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt fonction)

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Packages [](https://nuget.org/packages/)


Insérer un bit 0 dans un entier

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Description

Cette opération prend un entier, insère un 0 au bit `position` et retourne la valeur mise à jour sous la forme d’un entier.  Par exemple, l’insertion de 0 à la position 2 dans le nombre 10 (10$ _ {10} = 1010_ {2} $) retourne le nombre 18 ($18 _ {10} = 10010_ {2} $).

## <a name="input"></a>Entrée

### <a name="position--int"></a>position : [int](xref:microsoft.quantum.lang-ref.int)

Position à laquelle 0 est inséré


### <a name="value--int"></a>valeur : [int](xref:microsoft.quantum.lang-ref.int)

Valeur modifiée



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Valeur modifiée