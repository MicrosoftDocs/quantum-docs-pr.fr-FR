---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Opération DrawRandomBool
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706715"
---
# <a name="drawrandombool-operation"></a>Opération DrawRandomBool

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Packages [](https://nuget.org/packages/)


Pour une probabilité de réussite donnée, retourne une seule version d’essai de Bernoulli qui est vraie avec la probabilité donnée.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Entrée

### <a name="successprobability--double"></a>successProbability : [double](xref:microsoft.quantum.lang-ref.double)

Probabilité avec laquelle `true` doit être retourné.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` avec la probabilité `successProbability` et `false` avec la probabilité `1.0 - successProbability` .