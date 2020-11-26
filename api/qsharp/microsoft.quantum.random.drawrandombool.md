---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Opération DrawRandomBool
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192959"
---
# <a name="drawrandombool-operation"></a>Opération DrawRandomBool

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Pour une probabilité de réussite donnée, retourne une seule version d’essai de Bernoulli qui est vraie avec la probabilité donnée.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Entrée

### <a name="successprobability--double"></a>successProbability : [double](xref:microsoft.quantum.lang-ref.double)

Probabilité avec laquelle `true` doit être retourné.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` avec la probabilité `successProbability` et `false` avec la probabilité `1.0 - successProbability` .